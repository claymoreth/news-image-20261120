# VALIDATION — news-image-20261120 entry

## Final image (v4, 21 Nov 2026 ~01:05 WIB)

- **Path:** `out/entry.png` (also verified at the default `/output/entry.png`)
- **Format:** PNG, colour type 2 (RGB), bit depth 8
- **Dimensions:** 1024 × 1024 px (exact)
- **File size:** 56,119 bytes (≤ 1 MiB — 5.4% of the limit)
- **SHA-256:** `8c2c520f4017fc9a413ba4efaa1b763d8e6bc55d44efbc14ded2dd74d24e63de`

## Determinism (two runs, byte-for-byte)

| Run | Output | SHA-256 |
|-----|--------|---------|
| 1 | `/tmp/run1/entry.png` | `8c2c520f…e63de` |
| 2 | `/tmp/run2/entry.png` | `8c2c520f…e63de` |
| default path | `/output/entry.png` | `8c2c520f…e63de` |
| repo copy | `out/entry.png` | `8c2c520f…e63de` |

All four outputs are identical. No timestamp, no randomness, no
environment-dependent data in the image or the PNG stream.

## Static checks

- **Imports:** only `math`, `os`, `struct`, `zlib` (Python standard
  library). No third-party imports.
- **Network:** grep for `socket|urllib|requests|http|urlopen|ftp` in
  `main.py` returns nothing. The program makes no network requests.
- **External files/fonts:** none. The font is defined in-code; all
  illustrations and the map are drawn procedurally.
- **Runtime:** ~1.3 s per run. Local Python is 3.12.3; the code uses
  only stdlib features available in Python 3.13 (no version-specific
  syntax), so it runs identically under 3.13.

## Visual inspection (image read + 2× zoom crops + pixel measurement)

- All 8 story cards: headline (2 lines), deck/summary and source line
  fit inside their card borders; no clipped or overlapping text.
- Numbers strip: label descenders end at row 235, strip bottom edge
  at 242 (6 px margin).
- ALSO panel: all 10 bullets end at row 958, panel bottom at 972
  (14 px margin); no overlap with the footer.
- Map: 8 numbered pins visible; Europe cluster (pins 1, 4, 5, 6, 7)
  readable; legend lines below the map complete.
- DATE CHECK box: full body text + bottom note fit inside the border.
- Footer: single line, no overlap, ends well above the image edge.
- Spelling/facts: all visible text checked against the 8 verified
  stories; no unverified claims (no Bitcoin price, no 19-Nov stories
  presented as 20-Nov news).

## Revision history (what was fixed after visual inspection)

- **v1 → v2:** text was too thin to read (stroke weights raised
  everywhere: body 2 → 2.5, masthead 4 → 5, date 6 → 7, sources
  1 → 1.5–2); lead decks overflowed their cards (trimmed to ≤130
  chars, deck moved up, line height 16 → 15); medium kickers
  overflowed the card's right edge (kicker size 11 → 10 for medium
  cards); numbers-strip labels were clipped by the band edge (strip
  58 → 64 px, labels repositioned); Kenya illustration read as the
  letters "A" and "T" (derrick rebuilt as a lattice tower with
  cross-bracing and crown, acacia given a wide flat domed canopy);
  Poland redrawn in a centred sub-rect for truer proportions; COP
  globe de-crosshaired (vertical line removed, land blobs enlarged).
- **v2 → v3:** ALSO panel overflowed past the footer (measured: text
  reached row 1023; rewrote as 10 one-line bullets at 10 px);
  numbers-strip labels still only had a 3 px margin (strip 64 → 66 px).
- **v3 → v4:** last ALSO bullet wrapped to a second line ("years"
  alone); shortened to "UK-EU youth scheme: ages 18-31" so all 10
  bullets are single lines.

## Known limitations (honest notes)

- The vector font is a hand-drawn single-stroke design; at small sizes
  it has a deliberately sketch-like character rather than a typeset
  serif look. All text remains legible at full size and at ~300 px
  thumbnail scale.
- World-map pins in crowded Europe are nudged a few degrees on the
  schematic map so the numbered discs do not overlap (Kyiv, Warsaw,
  Brussels, Rome, Antalya). Positions remain in the correct countries.
- The program was tested locally with Python 3.12.3 (no Python 3.13
  binary exists on this machine); the code is 3.13-compatible by
  construction (stdlib only, no new syntax).

## Stop conditions honoured

No commit, no push, no remote repository, no submission, no signing,
no keypair or credential access. The entry exists only as local files
in this directory.
