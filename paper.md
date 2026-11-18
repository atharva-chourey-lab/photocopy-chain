# The Photocopy Chain: The Mammal Brain-Mass Canon Disagrees With Itself on 30% of Shared Species, and Three-Quarters of Its Most-Cited Values Cannot Be Traced to a Measurement

Author: Atharva Chourey
Affiliation: Atharva Chourey Lab (independent research lab)

*Manuscript — not yet peer-reviewed.*

## Abstract

Comparative neuroscience treats three compilations — Burger et al. (2019), Smaers et al. (2021) and Tsuboi et al. (2018) — as the primary record of mammal brain mass. We pre-registered two tests of that record before downloading any data. Test A diffed the three canons against each other: of the 1,467 species present in at least two canons, 447 (30.47%) disagree by more than 5% on brain mass, and 19.3% disagree by more than 10% — against a registered kill threshold of 3%. Test B traced a pre-registered random sample of 60 Burger values to their sources: only 15 (25.0%) terminate in a work whose authors themselves measured brains or endocranial volumes; the remaining 75% terminate in earlier compilations — against a registered kill threshold of 85% traceable. Both legs fail their kill conditions decisively. Burger's 1,552 values cite only 30 distinct first sources, and five compilations supply 82.6% of them. The canon's worst errors — an owl monkey at 6.7× its measured brain mass, a laboratory rat at 3.4× — are traceable, but to mislabelled or unreplicated specimen records from 1908 and 1940 that no later compiler re-checked. No canon is the accurate one: each dissents from the other two, and one carries a clade-shaped divergence across the pinnipeds. The mammal brain-mass canon is a photocopy chain, and any analysis built on a single canon inherits whichever copy it happened to open.

*Keywords:* brain mass; comparative neuroanatomy; data provenance; Burger et al. 2019; Smaers et al. 2021; Tsuboi et al. 2018; pre-registration; measurement

## 1. Introduction: a canon nobody re-measures

Species-level brain-mass values are load-bearing inputs to comparative neuroscience: encephalisation quotients, allometric exponents, and correlations between brain size and life history, diet, and sociality are all computed from them. Since 2018, that input has meant, in practice, one of three compilations. Burger et al. (2019, *Journal of Mammalogy*) assembled brain masses for 1,552 mammal species; Smaers et al. (2021, *Science Advances*) assembled values for roughly 1,400 living and extinct mammals; Tsuboi et al. (2018) published class workbooks covering 1,409 mammal species aggregated from specimen-level rows.

None of the three is a measurement programme. Each is a compilation of earlier compilations and primary sources, assembled under time pressure and checked, at best, against the next source encountered. Burger et al.'s own methods state the practice plainly: extracted values were checked between the initial source and "the second source encountered", and the authors "did not go beyond" the second source. The canonical dataset was therefore verified against the next compilation to hand — never systematically against a primary measurement of an actual brain.

That practice makes a testable prediction. If the chain of copying is faithful, the three canons should agree with each other wherever they cover the same species, and a sampled value should be traceable, hop by hop, to a work that measured a brain. If the chain is lossy — if errors enter at compilation boundaries and are then canonised — the canons should disagree at rates far above measurement noise, and sampled values should terminate in compilations whose own per-species sources are not openly resolvable.

This paper runs both tests under a pre-registration fixed before any dataset file was downloaded. The registration set the kill conditions in advance: the photocopy-chain claim dies if fewer than 3% of shared species disagree by more than 5%, or if at least 85% of sampled Burger values prove primary-traceable. Neither condition came close to firing.

## 2. Methods

### 2.1 The three canons

Burger et al. 2019 (1,552 species; data on Dryad, doi:10.5061/dryad.2r62k7s), Smaers et al. 2021 (1,418 species in the data supplement as downloaded), and Tsuboi et al. 2018 (mammal workbook; 1,409 species after the aggregation rule below). Provenance of each file, including access route and checksum verification, is given in SOURCES.md.

### 2.2 Test A — the three-way diff

Species were matched across canons by strict binomial only, per the registration; 22 epithets shared across canons under different genera (probable reassignments) were left unmatched and counted, not merged. Tsuboi's workbook keeps sources as separate specimen-level rows; its species values are sample-size-weighted means of its adult species×source rows (mass preferred; volume ×1.036 where mass is absent) — an implementation rule fixed before the diff ran and logged in the analysis script. A species is discordant if any pairwise relative difference among the canons covering it exceeds 5%. Smaers' 107 fossil species never enter the diff (Burger and Tsuboi are extant-only), so the shared-species rate is the registered primary rate.

### 2.3 Test B — provenance sample

A random sample of 60 Burger rows was drawn by script (seed 20261117) before any value was inspected. Each value's cited chain was traced hop by hop. A value is **primary-traceable** if the chain terminates in an identifiable work whose authors themselves weighed or measured brains or endocranial volumes; **compilation-only** if every openly resolvable link is itself a compilation, or the compilation's per-species attribution is not openly resolvable. A hop was credited only when an openly accessible per-species attribution was actually inspected, never assumed.

## 3. Results

### 3.1 Test A: 30.47% discordance

Overlaps: Burger∩Smaers 1,168 species; Burger∩Tsuboi 1,277; Smaers∩Tsuboi 1,024; 1,467 species in at least two canons; 1,001 in all three.

| Comparison | n shared | >5% | >10% |
|---|---|---|---|
| All shared species (≥2 canons) | 1,467 | **30.5%** (447) | 19.3% |
| Species in all three canons | 1,001 | 36.7% | — |
| Burger vs Smaers | 1,168 | 24.6% | 14.6% |
| Burger vs Tsuboi | 1,277 | 20.1% | 10.2% |
| Smaers vs Tsuboi | 1,024 | 28.8% | 16.5% |

Among discordant species present in all three canons where the other two agree within 5%, Smaers is the lone dissenter 137 times, Tsuboi 100, Burger 70; in 60 species all three disagree with each other. No canon is "the accurate one".

### 3.2 The worst disagreements are old errors, canonised

| Species | Burger (g) | Smaers (g) | Tsuboi (g) | What happened |
|---|---|---|---|---|
| *Aotus lemurinus* (owl monkey) | **113.5** | 16.30 | 16.92 | Burger ← Boddy ← Crile & Quiring 1940's "Aotus" rows (118 g, n=6; 109 g, n=11) — specimens that cannot be owl monkeys (~17 g brain). Burger's value is the exact mean of those two rows: **6.7× too big**. Burger's "second source" check for this row was also Crile & Quiring 1940. |
| *Melogale personata* (ferret-badger) | **61.4** | 13.83 | 14.33 | Burger ← Pérez-Barbería et al. 2007. Burger's body mass for the species (14,042 g for a ~2 kg animal) is inflated in proportion — a corrupted upstream row, photocopied whole. |
| *Phocoena phocoena* (harbour porpoise) | **1,735** | 477 | 821.5 | Burger ← Boddy ← Crile & Quiring 1940 (single specimen, 1,735 g). Tsuboi's own source rows span 477 to 1,735 g; Smaers took the modern value. Three canons, three porpoise brains spanning 3.6×. |
| *Rattus norvegicus* (lab rat) | **8.03** | 2.33 | 2.87 | Burger ← Boddy ← Warncke 1908's adult "rat" rows (8.75, 7.3 g); Burger is their exact mean. A rat brain is ~2 g. The canon's rat is **3.4× too big**, via 1908. |
| *Castor canadensis* (beaver) | **52.21** | 21.40 | 45.23 | Burger ← Boddy ← Crile & Quiring's single adult row (52.21 g, n=2); Boddy also holds a 36.5 g value, not used. Smaers is 2.4× below Burger. |
| *Otomys angoniensis* | 0.42 | **1.42** | 0.42 | Smaers carries an apparent digit slip (0.42 → 1.42); Burger and Tsuboi agree exactly. |

**The pinniped split is systematic and clade-shaped.** For most fur seals, sea lions and many true seals, Smaers' brain mass is 0.47–0.72× Burger's (e.g. *Arctocephalus philippii* 415 → 194 g; *Phoca vitulina* 315 → 171 g; *Zalophus californianus* 405 → 226 g), while a minority of pinniped species agree exactly. One of the two canons is using a different ruler for an entire clade; the published encephalisation literature for pinnipeds inherits whichever one it happened to open.

Within Tsuboi's own workbook, for the 362 species with rows from two or more different references, Tsuboi's rows disagree by more than 5% in 89.2% of species. This is descriptive context, not a verdict input — Tsuboi mixes methods and a few rows are mis-scoped — but it shows the disagreement is already inside the most transparent compilation, before any cross-canon copying.

### 3.3 Test B: 25.0% primary-traceable

Of the 60 sampled Burger values: **15 primary-traceable (25.0%), 45 compilation-only (75.0%), 0 untraceable.**

The largest block is Boddy 2012 (20 sampled rows). Burger's species values reproduce exactly as means of the adult measurement rows in Boddy's own open database (Zenodo 5000429) — *Aotus lemurinus* (118+109)/2 = 113.5; *Rattus norvegicus* (8.75+7.3)/2 = 8.03 — and Boddy attributes every row to its source, so the hop is executable. It splits the 20 rows exactly in half: 10 primary-traceable (rows that are original measurements: Crile & Quiring 1940, Warncke 1908, Hrdlička 1925, Stephan et al. 1981, and others) and 10 compilation-only (rows sourced to Mace et al. 1981, Mace & Eisenberg 1982, or Bininda-Emonds 2000, whose own per-species sources are not openly resolvable). The remaining blocks: 5 more primary-traceable (Isler et al. 2008; Matějů et al. 2016 — authors who measured endocranial volumes themselves) and 35 more compilation-only, spread across Jones & MacLarnon 2004, Isler & van Schaik 2012, the Ashwell/Weisbecker re-compilation layer, Pérez-Barbería 2007, and others.

Structurally, Burger's 1,552 values cite only **30 distinct first sources**, and five compilations supply 1,282 of them (82.6%): Boddy 2012 (498), Jones & MacLarnon 2004 (302), Isler & van Schaik 2012 (190), Ashwell/Weisbecker (183), Isler et al. 2008 (109). The "1,552-species dataset" is, to first order, five earlier datasets re-averaged.

### 3.4 Traceability is not accuracy

The three worst Burger errors in Test A (*Aotus*, *Rattus*, *Phocoena*) are all primary-traceable — to Crile & Quiring 1940 and Warncke 1908 specimen records that no modern ruler corroborates. The canon therefore fails two ways at once: three-quarters of it never touches a measurement, and some of the quarter that does traces to century-old specimen records that were wrong, or mislabelled, at the source. Nobody re-measures; the chain only copies.

## 4. Verdict against the registered kill conditions

| Leg | Kill requires | Observed | Result |
|---|---|---|---|
| Test A — discordance (>5%) among shared species | < 3% | **30.47%** (447/1,467) | Kill fails by 10× |
| Test B — sampled Burger values primary-traceable | ≥ 85% | **25.0%** (15/60) | Kill fails by 60 points |

Either leg alone decides the registered test; both failed decisively. The finding is not the smaller case of one compilation indicted: all three canons dissent from each other, Burger's provenance fails across every major source block, and Smaers carries its own clade-shaped divergence and digit slips.

In one sentence: 30% of the mammal brain-size canon's species carry two different brains depending on which canon you open, and 75% of its most-cited values cannot be traced to any measured brain — while its worst errors trace cleanly to mislabelled specimens weighed in 1908 and 1940.

## 5. Caveats (declared)

- The headline does not depend on the Tsuboi aggregation rule: Burger vs Smaers alone discord at 24.6%.
- Smaers data S1 stores ln(mass in g); verified against *Homo sapiens* (65,000 g body / 1,330 g brain after exponentiation).
- All shared species are extant by construction, so the shared-species rate is the registered primary (extant) rate.
- Test B credits a hop only when an openly accessible per-species attribution was actually inspected. A small number of compilation-only rows may rest on primary measurements one hop further down; resolving every one could raise the primary-traceable share by a few points, nowhere near the 85% threshold.

## 6. Data availability

The pre-registration, analysis scripts, the full joined diff table for all 1,467 shared species, and the 60-value provenance sample with its complete trace are preserved in the lab's project record and summarised in SOURCES.md. Source datasets: Burger et al. 2019 via Dryad (doi:10.5061/dryad.2r62k7s; file checksums verified against Dryad's record), Smaers et al. 2021 data S1 via the Internet Archive's capture of the *Science Advances* supplement, Tsuboi et al. 2018 mammal workbook via the authors' Springer Nature figshare deposit (article 6803276; checksum verified), Boddy database via Zenodo record 5000429.

## Acknowledgements

This work is a human–AI collaboration of the Atharva Chourey Lab: the audit was designed, pre-registered and executed jointly by the lab's researcher and an AI research partner (Muse), with all source readings and computations preserved for inspection.

## References

- Burger, J.R. et al. 2019. The allometry of brain size in mammals. *Journal of Mammalogy* 100. Data: Dryad doi:10.5061/dryad.2r62k7s.
- Smaers, J.B. et al. 2021. The evolution of mammalian brain size. *Science Advances* 7.
- Tsuboi, M. et al. 2018. Breakdown of brain–body allometry and the evolution of relative brain size in vertebrates. *Nature Ecology & Evolution* 2. Mammal workbook: Springer Nature figshare, article 6803276.
- Boddy, A.M. et al. 2012. Comparative analysis of mammalian brain data. Database: Zenodo record 5000429.
- Crile, G. & Quiring, D.P. 1940. A record of the body weight and certain organ and gland weights of 1,281 animals. *Ohio Journal of Science* 40.
- Warncke, P. 1908. Mitteilungen neuer Gehirnuntersuchungen an Säugern. (As cited in Boddy 2012.)
