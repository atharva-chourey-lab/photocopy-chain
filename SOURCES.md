# Sources Map — The Photocopy Chain (mammal brain-mass canon audit)

Author: Atharva Chourey
Affiliation: Atharva Chourey Lab (independent research lab)

*Manuscript — not yet peer-reviewed.*

This file maps every key number, verdict and reference in `paper.md` to the source file it was taken from. Nothing in the paper was taken from a source outside this list.

## Primary sources

- `~/workspace/brain-scan-comparison/projects/photocopy-chain/PREREGISTRATION.md` — the registered test: fixed 2026-11-17 BEFORE any dataset file was downloaded for this project. Kill conditions: Test A dies if discordance (>5%) among shared species is < 3%; Test B dies if ≥ 85% of sampled Burger values are primary-traceable.
- `~/workspace/brain-scan-comparison/projects/photocopy-chain/RESULTS.md` — the run record: verdict, both test legs, worst-case table, pinniped split, within-Tsuboi spread, caveats, and file provenance. The paper follows it throughout.
- `~/workspace/brain-scan-comparison/projects/photocopy-chain/results/joined_diff.csv` — all 1,467 shared species with per-canon values and pairwise differences. The paper's headline discordance was recomputed from this file during the publication build: 447/1,467 = 30.47% (>5%), 283/1,467 = 19.3% (>10%) — matches RESULTS.md.
- `~/workspace/brain-scan-comparison/projects/photocopy-chain/results/provenance_sample.csv` and `provenance_trace.csv` — the 60-value pre-registered sample (seed 20261117) and its full trace. Recomputed during the publication build: 15 primary-traceable / 45 compilation-only = 25.0% — matches RESULTS.md.
- `~/workspace/brain-scan-comparison/projects/photocopy-chain/scripts/analyse.py` (Test A + sample draw), `scripts/trace.py` (Test B).

## Source datasets (as recorded in RESULTS.md §5)

- Burger et al. 2019 data + references from Dryad doi:10.5061/dryad.2r62k7s (Dryad's download endpoint is bot-gated; files were obtained from a public course mirror and verified byte-identical — CSV MD5 3a68156bcdbc6531895c51fdaf2fb111 matches Dryad's own record).
- Smaers et al. 2021 data S1 via the Internet Archive's capture of the *Science Advances* supplement (science.org is access-gated).
- Tsuboi et al. 2018 mammal workbook from the authors' Springer Nature figshare deposit (article 6803276; MD5 ad4c91be6e79e8d1c3ff03f5ab946ae6 matches the figshare record).
- Boddy et al. 2012 database from Zenodo record 5000429.

## Key numbers and their sources

| Claim in paper | Value | Source file |
|---|---|---|
| Species in ≥2 canons | 1,467 (1,001 in all three) | RESULTS.md §Test A; joined_diff.csv (recomputed) |
| Discordance >5% | 30.47% (447/1,467) | joined_diff.csv (recomputed) |
| Discordance >10% | 19.3% (283/1,467) | joined_diff.csv (recomputed) |
| Pairwise discordance | B–S 24.6% · B–T 20.1% · S–T 28.8% | RESULTS.md §Test A |
| Primary-traceable share | 25.0% (15/60) | provenance_trace.csv (recomputed) |
| Burger first sources | 30 distinct; top five supply 82.6% (1,282/1,552) | RESULTS.md, "Structure of the canon" |
| *Aotus lemurinus* | Burger 113.5 g = mean of Crile & Quiring 1940 rows 118/109 g; ~6.7× | RESULTS.md, worst disagreements |
| *Rattus norvegicus* | Burger 8.03 g = mean of Warncke 1908 rows 8.75/7.3 g; ~3.4× | RESULTS.md, worst disagreements |
| Pinniped ratio band | Smaers 0.47–0.72× Burger for most of the clade | RESULTS.md, pinniped split |
| Within-Tsuboi spread | 89.2% of 362 multi-source species disagree >5% internally (descriptive only) | RESULTS.md, within-Tsuboi spread |
| Kill thresholds | Test A < 3%; Test B ≥ 85% | PREREGISTRATION.md |

## Novelty and framing notes

- The paper claims a pre-registered cross-canon diff and provenance trace of the three named compilations — nothing wider. It does not claim any single canon is correct; §3.1 reports each canon dissenting from the other two.
- The within-Tsuboi figure is carried in the paper as descriptive context with its caveat (mixed methods, some mis-scoped rows), exactly as the source record states it — it is not a verdict input.
- Canon file sizes (Burger 1,552 / Smaers 1,418 / Tsuboi 1,409 species) are as downloaded and recorded in RESULTS.md.
