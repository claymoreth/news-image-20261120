# THE WORLD IN ONE DAY — Friday 20 November 2026

An original editorial front page that sums up the world's news for
**Friday 20 November 2026** in a single 1024×1024 image. Built for the
make.fun bounty `news-image-20261120` ("Sum up 20 November's world news
in one image").

## What it is

A one-page newspaper front page, drawn entirely by code:

- **Masthead + giant date** — "FRIDAY 20 NOVEMBER 2026" dominates the page.
- **Key-numbers strip** — 3 bridges, 300,000+ evacuated, −6.2% Taiex,
  £5.1bn, 20,000 barrels/day.
- **3 illustrated lead stories** — Kyiv's bridges struck, Cyclone Akvan's
  landfall, the AI sell-off in Asian markets.
- **5 illustrated secondary stories** — UK–EU reset, COP31 overtime,
  Russian missiles in Poland, Italy's general strike, Kenya's first oil.
- **World map** with 8 numbered pins matching the 8 stories.
- **"ALSO ON FRIDAY 20 NOVEMBER"** index of 10 further verified facts.
- **"DATE CHECK"** box explaining that the ICJ Myanmar ruling, the
  Shenzhen declaration and the GTA VI launch were Thursday 19 November
  news and are therefore deliberately left out; and that the final COP31
  text had not been agreed at press time.

## How it is made

`main.py` is a single self-contained Python 3 program (standard library
only — `math`, `os`, `struct`, `zlib`). It contains:

- a hand-written **PNG encoder** (zlib compression, CRC32 chunks);
- a hand-defined **single-stroke vector font** (A–Z, a–z, 0–9 and common
  punctuation, including £, €, •, → and —);
- drawing primitives (lines, discs, polygons, arcs, gradients);
- eight original procedural illustrations (night bridges under attack,
  cyclone spiral, falling market chart, UK–EU bridge, COP globe,
  Poland map, strike crowd, Turkana oil derrick) and a simplified
  world map.

No third-party packages, no network access, no external files or fonts.
Two runs produce byte-for-byte identical output (no timestamps, no
randomness).

## Run

```sh
python3 main.py
```

Writes `entry.png` to `MAKEFUN_OUTPUT_DIR` (default `/output`).
Local test: `MAKEFUN_OUTPUT_DIR=out python3 main.py`.

## Stories (all verified, Friday 20 November 2026)

1. **Kyiv** — Russian ballistic missiles hit three Dnipro bridges;
   110+ missiles, 400+ drones; 3 dead in Kyiv, 8 across Ukraine.
   Sources: Reuters, AP.
2. **Cyclone Akvan, Odisha** — landfall near Gopalpur, winds 70–80 km/h
   gusting to 90; 300,000+ evacuated; no deaths reported.
   Source: India Meteorological Department.
3. **AI sell-off** — Taiex −6.2%, Nikkei −5.1%, Kospi −5.2%;
   Anthropic down ~10% in premarket trading. Sources: Reuters, Morningstar.
4. **UK–EU reset** — food standards, carbon markets, youth scheme
   (18–31); worth £5.1bn a year by 2040. Source: Reuters.
5. **COP31, Antalya** — talks into overtime; draft cut 144 → 80
   paragraphs, fossil fuels dropped; US absent a second year.
   Sources: Reuters, UN News.
6. **Poland** — two Russian missiles and a jet drone entered Polish
   airspace; no casualties; F-16s and Gripens scrambled.
   Sources: Polish Defence Ministry, Reuters.
7. **Italy** — 24-hour CGIL general strike in 100+ cities against a
   €26bn budget. Sources: Reuters, AP.
8. **Kenya** — first oil drilling begins at Amosing, Turkana;
   commercial output due 1 December; target 20,000 barrels/day.
   Sources: Capital FM, People Daily.

## Files

- `main.py` — the generator (1,075 lines).
- `LICENSE` — MIT.
- `README.md` — this file.
- `VALIDATION.md` — verification log (dimensions, size, SHA-256,
  determinism, revision history).

## License

MIT — see `LICENSE`.
