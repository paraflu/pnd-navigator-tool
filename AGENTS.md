# PND Navigator Patcher

Single-page web tool (vanilla HTML/CSS/JS) for patching a byte in a Renault GPS
binary inside a ZIP archive. No build system, no package manager, no tests.

## Commands

No dev commands. Open `index.html` in a browser to test.

## Architecture

- **`index.html`** — entire application: markup, styles, and logic are all inline
- **JSZip 3.10.1** loaded from CDN (`cdnjs.cloudflare.com`)
- **CI** (`.gitlab-ci.yml`): GitLab Pages — simply copies all files into `public/`
- **Live demo**: `https://paraflu.github.io/pnd-navigator-tool/`

## Patch logic

Search is recursive: walks ZIP entries, recurses into nested ZIPs, matches the
first file whose basename contains `pndnavigator` (case-insensitive, non-ZIP).

Actual patch applied in code:

| Field        | Value              |
|--------------|--------------------|
| File offset  | `0x00402928`       |
| Original     | `0xD6`             |
| Replacement  | `0xB9`             |

The README documents an older target (`0xD6`→`0xB9` at `0x2920`). The code is
the source of truth — the offset and values have been corrected over multiple
commits but the README was not updated.

## Known quirks

- README documents offset `0x2920` — code uses `0x00402928`.
