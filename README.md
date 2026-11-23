# News in One Image — 22 November 2026

[![make.fun · news-image-20261122](https://make.fun/badge/news-image-20261122.svg)](https://make.fun/bounty/news-image-20261122?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261122)
[![rank](https://make.fun/badge/news-image-20261122/heraltmosses54-pixel/news-image-20261122/rank.svg)](https://make.fun/bounty/news-image-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261122)
[![reward](https://make.fun/badge/news-image-20261122/heraltmosses54-pixel/news-image-20261122/reward.svg)](https://make.fun/bounty/news-image-20261122?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261122)

A small Python program that sums up the world's news of Sunday 22 November 2026
in a single image: a dense 1024x1024 newspaper front page drawn entirely with
code — **23 stories from 6 continents on one page**.

Run it:

    python3 main.py

It writes `entry.png` (1024x1024) next to the script. Pure Python 3 standard
library: no Pillow, no font files, no network access, no randomness — every
run produces byte-identical output. Text is composed at runtime from a glyph
atlas that was rendered once per style/size at build time, packed into one
image, quantised to 4-bit alpha and embedded as base64; the program only
decodes the atlas, blits glyphs into a framebuffer, paints the rules, boxes
and a dotted world map, and writes the PNG.

What's on the page:

- **Lead story** — COP31 ends in Antalya with no deal after 48 hours of
  overtime talks, the EU refusing any text without a fossil-fuel phase-out.
- **12 story cards** — Democrats take 258 US House seats (largest majority
  since 1992); Russian corvette Merkury sunk off Libya; apartment block hit
  near Kyiv; Iran strikes a Bahrain site; Banten candy factory fire kills 24;
  AI fears sink global stocks; BepiColombo reaches Mercury orbit; Delta
  delays top 1,000 flights at Atlanta; Trump, Putin and Xi to meet at APEC
  Shenzhen; allies rally for Kyiv in Berlin; NDA sweeps the Bihar election;
  OpenAI ships GPT-6.2 Astra and Sol.
- **The day on the map** — a dotted world map with a red marker for every
  story on the page, plus a by-the-numbers rail (258 House seats, 24 dead in
  Banten, 1,000+ delayed flights).
- **Around the world in brief** — nine one-liners: Madrid's first general
  strike in 14 years, the Krakow square shooting, the Abu Dhabi prisoner
  swap, Pakistan's judicial-capture report, Caracas protests, RAF jets for
  Saudi cities, French cost-of-living unrest, Bumrah's Wellington return and
  deadly floods in eastern Spain.
- **Sport** — Bumrah's three wickets leave New Zealand 70 for 5.

Entry for the make.fun bounty "Sum up 22 November's world news in one image"
(news-image-20261122). MIT licensed.
