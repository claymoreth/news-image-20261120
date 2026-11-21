[![make.fun · news-image-20261120](https://make.fun/badge/news-image-20261120.svg)](https://make.fun/bounty/news-image-20261120?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120)
[![rank](https://make.fun/badge/news-image-20261120/claymoreth/news-image-20261120/rank.svg)](https://make.fun/bounty/news-image-20261120/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120)
[![reward](https://make.fun/badge/news-image-20261120/claymoreth/news-image-20261120/reward.svg)](https://make.fun/bounty/news-image-20261120?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120)

# THE WORLD IN ONE DAY — Friday 20 November 2026

An original editorial front page that sums up the world's news for
**Friday 20 November 2026** in a single 1024×1024 image. Built for the
make.fun bounty [`news-image-20261120`](https://make.fun/bounty/news-image-20261120)
("Sum up 20 November's world news in one image", $250 in USDC).

## What it is

A one-page newspaper front page, drawn entirely by code:

- **Masthead + giant date** — "FRIDAY 20 NOVEMBER 2026" dominates the page.
- **Key-numbers strip** — 40 stories, 8 regions, 300,000+ evacuated,
  5.1% Asian markets fall, £5.1bn UK–EU deal, 118 countries.
- **3 illustrated lead stories** — Kyiv's bridges struck, Cyclone Akvan's
  landfall, the AI sell-off in Asian markets.
- **5 illustrated secondary stories** — UK–EU reset, COP31 overtime,
  Russian missiles in Poland, Italy's general strike, Kenya's first oil.
- **5 illustrated smaller stories** — Türkiye, India, Australia, Brazil,
  Mexico.
- **World map** with coloured teardrop pins marking where it happened.
- **"ALSO ON FRIDAY 20 NOVEMBER — 27 MORE STORIES"** index.
- **"DATE CHECK"** box explaining that the ICJ Myanmar ruling, the
  Shenzhen declaration and the GTA VI launch were Thursday 19 November
  news and are therefore deliberately left out; and that the final COP31
  text had not been agreed at press time.

## How it is made

`main.py` is a single self-contained Python 3 program (standard library
only — `math`, `os`, `struct`, `zlib`). It contains:

- a hand-written **PNG encoder** (zlib compression, CRC32 chunks);
- **real Liberation font outlines** (Serif Bold, Serif Italic, Serif
  Regular, Sans Bold, Sans Regular) embedded as data — see
  `FONT-LICENSE.txt` (SIL Open Font License);
- drawing primitives (lines, discs, polygons, arcs, gradients);
- thirteen original procedural illustrations (Kyiv dusk skyline, cyclone
  spiral, falling market chart, glowing globe, jets, robot arm, oil
  pumpjack, cargo ship, bar chart, solar panels, forest, pyramid) and a
  simplified world map.

No third-party packages, no network access, no external files or fonts.
Two runs produce byte-for-byte identical output (no timestamps, no
randomness).

## Run

```sh
python3 main.py
```

Writes `entry.png` to `MAKEFUN_OUTPUT_DIR` (default `/output`).
Local test: `MAKEFUN_OUTPUT_DIR=out python3 main.py`.

## Files

- `main.py` — the generator (1,605 lines).
- `LICENSE` — MIT.
- `README.md` — this file.
- `VALIDATION.md` — verification log (dimensions, size, SHA-256,
  determinism, revision history).
- `FONT-LICENSE.txt` — Liberation fonts, SIL Open Font License 1.1.

## License

MIT — see `LICENSE`.
