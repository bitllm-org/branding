# Interface fonts

The site and the dashboard use these files, so that every OS shows the same letters. Copy them from
here: to `public/fonts/` in [bitllm-org/landing-page](https://github.com/bitllm-org/landing-page), and
through `scripts/fonts-css.sh` in [bitllm-org/bitllm](https://github.com/bitllm-org/bitllm).

| file | face | source |
|---|---|---|
| `jetbrains-mono-400.woff2` | Regular | JetBrains Mono v2.304 |
| `jetbrains-mono-400i.woff2` | Italic, for code comments | JetBrains Mono v2.304 |
| `jetbrains-mono-700.woff2` | Bold | JetBrains Mono v2.304 |
| `arimo-400.woff2` | Regular | Arimo, from google/fonts |
| `arimo-700.woff2` | Bold | Arimo, from google/fonts |

Only these faces ship, not a variable font. Weights 500 and 600 in the CSS resolve to Regular and Bold.

Arimo is the design Liberation Sans is based on. It is used here because Liberation reserves its font
name, which restricts subsetting. Both licenses are in this folder.

## How they were made

Arimo starts as a variable font, so make the two static weights first. Then subset with
[fonttools](https://github.com/fonttools/fonttools):

```sh
fonttools varLib.instancer "Arimo[wght].ttf" wght=400 -o Arimo-400.ttf --update-name-table
fonttools varLib.instancer "Arimo[wght].ttf" wght=700 -o Arimo-700.ttf --update-name-table

LATIN='U+0020-007E,U+00A0-00FF,U+0131,U+0152,U+0153,U+2013,U+2014,U+2018-201A,U+201C-201E,U+2022,U+2026,U+2039,U+203A,U+20AC,U+2122,U+2190-2193,U+2197,U+2212,U+2713'
MONO="$LATIN,U+2500-257F,U+2580-259F,U+25A0-25FF"

fonttools subset JetBrainsMono-Regular.ttf --unicodes="$MONO" \
  --layout-features='calt,ccmp,kern,liga,locl,mark,mkmk' \
  --flavor=woff2 --no-hinting --desubroutinize \
  --output-file=jetbrains-mono-400.woff2
```

Do the same for the other files, using `$LATIN` for Arimo. Add a character to the range if a page needs
one: anything missing falls back to a system font, and then that character differs by OS.
