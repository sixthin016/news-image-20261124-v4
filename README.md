# news-image-20261124 — v4

[![make.fun · news-image-20261124](https://make.fun/badge/news-image-20261124.svg)](https://make.fun/bounty/news-image-20261124?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261124)
[![rank](https://make.fun/badge/news-image-20261124/sixthin016/news-image-20261124-v4/rank.svg)](https://make.fun/bounty/news-image-20261124/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261124)
[![reward](https://make.fun/badge/news-image-20261124/sixthin016/news-image-20261124-v4/reward.svg)](https://make.fun/bounty/news-image-20261124?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261124)

Sum up the world's news of Tuesday 24 November 2026 in one image.

A newspaper front page drawn entirely in code. This is the fourth
iteration. v3 reached round 1 rank 11 of 7,302 (80.27%) — a strong
position — but its own gate found eight defects worth fixing before
the next round, and v4 fixes all eight without touching what made v3
win (its internal consistency: every count on the page agrees with
every other count).

## What changed against v3

- **Geneva pins out of the sea.** v3 nudged pins 9 and 10 off the
  Swiss landmass into the water west of Europe. Switzerland is ~7 px
  wide on this map, so any nudge leaves it; the two Geneva stories
  now share ONE pin at the true Geneva point, labelled "09·10" (the
  two Seoul stories share "13·31" the same way). The legend says so.
- **Seoul, not Tokyo, for the Kospi.** Story 31 now reads "Seoul:
  Kospi +6.3%, Nikkei +3% on Huang rally" — the Kospi is South
  Korea's index.
- **The "TO THE JUDGE:" line is gone.** The date-check box is one
  line now; the page speaks for itself.
- **Panel bodies carry a second fact.** Four bodies in v3 only
  repeated their headlines. Each now adds a fact from another story
  on the same page — the Nvidia rally lifting Seoul and Tokyo, the
  Java fire behind the Bayelsa toll, Tehran's missile threat behind
  the Jerusalem story. Nothing invented.
- **Eight-more spans six regions, not four.** Washington (Americas)
  and Jerusalem (Middle East) join as panels; the Java fire and the
  Hobart stadium move to the list. Region totals are unchanged —
  counts are over all 35 stories, not over panel slots.
- **The 24-story list is two columns, not three.** Each entry gets
  ~490 px of air instead of ~322 px; at 300 px wide the list stays
  readable.
- **Story 29 is Wellington.** The India v New Zealand first Test was
  played at the Basin Reserve, Wellington — not in India — so its
  region is Oceania. Region counts become 6+6+11+3+4+4+1 = 35, and
  the legend is computed from the data, so it still matches the map.
- **Lead 3 is Tuesday's news, not Sunday's.** The COP31 collapse was
  Sunday; Tuesday's news is the blame-trading that followed —
  Erdogan's groundwork claim, the EU's refusal of a weak text — and
  the lead now says so.

## What did not change

- Serif display + clean sans (real vector type: DejaVu outlines
  embedded as data, rasterised here with 4× supersampling — no
  bitmap or pixel font anywhere).
- 35 stories, 14 fields, DATE CHECK + UTC timeline + confidence
  badges per story, world map with numbered pins, legend.
- No collisions, by construction: kicker bars reserve a badge slot
  (asserted), every picture is painted inside a hard clip rectangle,
  and the pin checker verifies no two markers overlap and every pin
  sits on land (the Gulf pin marks the Gulf itself).
- Deterministic, stdlib-only, ~1 s runtime, no network, no clock.

## Run it

```
python3 main.py            # writes output/entry.png
python3 main.py out.png    # explicit path wins
```

The grader runs on a read-only checkout with `MAKEFUN_OUTPUT_DIR`
set; `main()` honours it. Two runs produce byte-identical output.

## The day in one line

HUANG RETURNS — NVIDIA +31% — DYMER TOLL 11 — COP31 FALLOUT
