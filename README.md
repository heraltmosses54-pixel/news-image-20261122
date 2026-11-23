[![make.fun · news-image-20261122](https://make.fun/badge/news-image-20261122.svg)](https://make.fun/bounty/news-image-20261122?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261122)
[![rank](https://make.fun/badge/news-image-20261122/heraltmosses54-pixel/news-image-20261122/rank.svg)](https://make.fun/bounty/news-image-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261122)
[![reward](https://make.fun/badge/news-image-20261122/heraltmosses54-pixel/news-image-20261122/reward.svg)](https://make.fun/bounty/news-image-20261122?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261122)

# THE WORLD — Sunday 22 November 2026

A single self-contained Python program that draws a complete
newspaper front page as a 1024×1024 PNG. One day of world news on
one page: the COP31 lead out of Antalya, twelve more stories in a
three-column grid, a dotted world map with a red marker for every
story location, a "By the Numbers" rail, an around-the-world briefs
band and a sport footer — 23 stories, six continents, one page.

## Running it

    python3 main.py

That writes `entry.png`. The output path can be redirected:

- `$OUTPUT` — used verbatim when set;
- otherwise `$MAKEFUN_OUTPUT_DIR/entry.png` when that variable is set;
- otherwise `/output/entry.png` when `/output` exists;
- otherwise `entry.png` next to the script.

## How it works

Everything is pure Python 3 standard library (`base64`, `json`,
`os`, `struct`, `zlib`) — no Pillow, no network, no fonts on disk
at runtime. The letterforms were rendered once from DejaVu into a
glyph atlas, quantised to 4-bit alpha, compressed, and embedded in
`main.py` as base64 alongside the per-glyph metrics. At runtime the
program decodes the atlas, alpha-blends glyphs into a bytearray
framebuffer, paints the layout (masthead, lead column, map rail,
story grid, briefs band, footer), and encodes the PNG itself with
`struct` and `zlib`.

The output is fully deterministic: no clocks, no randomness, no
environment-dependent data, so every run produces byte-identical
PNG bytes.
