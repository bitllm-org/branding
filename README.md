# BitLLM brand

The BitLLM mark is a dark code tile: a block **B**, a green terminal cursor, and a faint peer
graph. It pairs with the `BitLLM_` wordmark, where the underscore is the cursor.

![The BitLLM square mark](logo.png)

## Files

| file | use |
|---|---|
| `logo.svg` | primary square mark, 1024x1024, full bleed |
| `logo.png` | primary PNG export, 1024x1024 |
| `logo-512.png` | 512x512 PNG |
| `logo-128.png` | 128x128 PNG |
| `logo-rounded.svg` | rounded app-icon variant, 1024x1024 |
| `logo-rounded.png` | rounded PNG export, 1024x1024 |

The primary mark is full bleed so avatars and social profiles can crop it without showing a second
rounded edge. Use the rounded variant for desktop and mobile app icons.

## Wordmark

Set the wordmark as `BitLLM_` in a monospace face. The underscore is green (`#5ddb96`). In motion
it may blink like a terminal cursor. Do not remove it, replace it with a period, or set it in a
proportional font.

## Color

| token | value | use |
|---|---|---|
| tile | `#080b09` | mark background |
| ink | `#e6efe9` | the B |
| green | `#5ddb96` | cursor, peer dots, accents |
| line | `#26332b` | outer border |
| grid | `#dce6df` at 3.5% | graph paper texture |
| amber | `#e4b465` | optional secondary accent |
| sub | `#8b978f` | secondary text |

## Type

Monospace for the wordmark, code, and labels:

```text
ui-monospace, SFMono-Regular, "SF Mono", Menlo, Consolas, "Liberation Mono", monospace
```

The dashboard and docs use a system sans for running prose, with monospace for commands, numbers,
and headings.

## Usage

- Keep clear space equal to the width of the cursor block on every side.
- Use at least 32 px for the tile. Use 96 px or more when the peer dots should read.
- Do not rotate, outline, recolor, or add a shadow to the B or the cursor.
- Do not crop the cursor off the mark.
- The tile carries its own background. Place it on light or dark surfaces without removing it.
- The wordmark may sit next to the mark, but the mark also works on its own.

## Palette in context

The mark comes from the local dashboard: a terminal window with numbered steps, a model inventory,
a code editor, and a test console. The green is the cursor and the "online" state; amber marks
things that belong to you; red is an error. Keep those meanings when extending the system.
