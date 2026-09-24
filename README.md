# Elliptic curves by rank

A collection of elliptic curves over **Q** of rank 4 to 15, given by minimal
Weierstrass model together with explicit Mordell-Weil generators.

Every curve here has **proven** rank. For each one the listed generators are
verified to lie on the curve and to be independent, which gives the rank as a
lower bound, and a 2-descent upper bound matches it. Every model is the minimal
model, and no curve appears twice.

## Contents

| file | rank | curves | smallest log N | smallest naive height | smallest Faltings height | smallest log abs(disc) |
|---|---:|---:|---:|---:|---:|---:|
| `rank_4.tsv.gz` | [4](records/rank_4.md) | 577,645 | [12.364981](records/rank_4.md#smallest-conductor) | [21.574288](records/rank_4.md#smallest-naive-height) | [-0.173133](records/rank_4.md#smallest-faltings-height) | [13.058128](records/rank_4.md#smallest-absolute-discriminant) |
| `rank_5.tsv.gz` | [5](records/rank_5.md) | 410,274 | [16.762465](records/rank_5.md#smallest-conductor) | [24.317973](records/rank_5.md#smallest-naive-height) | [0.083690](records/rank_5.md#smallest-faltings-height) | [16.762465](records/rank_5.md#smallest-absolute-discriminant) |
| `rank_6.tsv.gz` | [6](records/rank_6.md) | 1,085,045 | [22.369530](records/rank_6.md#smallest-conductor) | [30.376041](records/rank_6.md#smallest-naive-height) | [0.582833](records/rank_6.md#smallest-faltings-height) | [22.643449](records/rank_6.md#smallest-absolute-discriminant) |
| `rank_7.part1.tsv.gz` .. `rank_7.part3.tsv.gz` | [7](records/rank_7.md) | 3,358,923 | [26.670318](records/rank_7.md#smallest-conductor) | [35.779031](records/rank_7.md#smallest-naive-height) | [1.036540](records/rank_7.md#smallest-faltings-height) | [28.235073](records/rank_7.md#smallest-absolute-discriminant) |
| `rank_8.part1.tsv.gz` .. `rank_8.part4.tsv.gz` | [8](records/rank_8.md) | 2,874,139 | [33.151079](records/rank_8.md#smallest-conductor) | [41.826383](records/rank_8.md#smallest-naive-height) | [1.511528](records/rank_8.md#smallest-faltings-height) | [33.644948](records/rank_8.md#smallest-absolute-discriminant) |
| `rank_9.part1.tsv.gz` .. `rank_9.part5.tsv.gz` | [9](records/rank_9.md) | 3,300,917 | [38.007861](records/rank_9.md#smallest-conductor) | [47.863736](records/rank_9.md#smallest-naive-height) | [1.982707](records/rank_9.md#smallest-faltings-height) | [39.095558](records/rank_9.md#smallest-absolute-discriminant) |
| `rank_10.part1.tsv.gz` .. `rank_10.part4.tsv.gz` | [10](records/rank_10.md) | 1,642,525 | [43.767868](records/rank_10.md#smallest-conductor) | [54.348977](records/rank_10.md#smallest-naive-height) | [2.510505](records/rank_10.md#smallest-faltings-height) | [45.376023](records/rank_10.md#smallest-absolute-discriminant) |
| `rank_11.part1.tsv.gz` .. `rank_11.part5.tsv.gz` | [11](records/rank_11.md) | 2,132,246 | [51.246420](records/rank_11.md#smallest-conductor) | [61.346666](records/rank_11.md#smallest-naive-height) | [3.041194](records/rank_11.md#smallest-faltings-height) | [51.246420](records/rank_11.md#smallest-absolute-discriminant) |
| `rank_12.part1.tsv.gz`, `rank_12.part2.tsv.gz` | [12](records/rank_12.md) | 602,061 | [57.764522](records/rank_12.md#smallest-conductor) | [68.672711](records/rank_12.md#smallest-naive-height) | [3.722319](records/rank_12.md#smallest-faltings-height) | [59.188359](records/rank_12.md#smallest-absolute-discriminant) |
| `rank_13.tsv.gz` | [13](records/rank_13.md) | 48,347 | [64.738469](records/rank_13.md#smallest-conductor) | [75.137429](records/rank_13.md#smallest-naive-height) | [4.245237](records/rank_13.md#smallest-faltings-height) | [65.837081](records/rank_13.md#smallest-absolute-discriminant) |
| `rank_14.tsv.gz` | [14](records/rank_14.md) | 3,115 | [72.303161](records/rank_14.md#smallest-conductor) | [82.371945](records/rank_14.md#smallest-naive-height) | [4.863211](records/rank_14.md#smallest-faltings-height) | [73.720054](records/rank_14.md#smallest-absolute-discriminant) |
| `rank_15.tsv.gz` | [15](records/rank_15.md) | 26 | [81.565498](records/rank_15.md#smallest-conductor) | [92.182205](records/rank_15.md#smallest-naive-height) | [5.637976](records/rank_15.md#smallest-faltings-height) | [82.746402](records/rank_15.md#smallest-absolute-discriminant) |

16,035,263 curves in total.

Every figure in the table links to the ten smallest curves of that rank in that
category, with their a-invariants, exact conductors and full generators, under
[`records/`](records/). The four minima in each row are taken independently over
that rank, so they are generally attained by four different curves. Heights are natural logarithms.
The naive height is log max(abs(c4)^3, c6^2), and abs(disc) is the absolute
value of the minimal discriminant. The Faltings height is the unstable one,
normalized as

    h_Fal(E) = -(1/2) log abs(Im(conj(w1) w2)),

with w1, w2 a basis of the period lattice of the minimal model, which is the
normalization used by the Elliptic Curve Rank Leaderboard at
https://elliptic-rank.icarm.cloud. It is negative for some rank 4 curves.

## Format

Tab-separated, gzipped, one curve per line, sorted by ascending conductor.
The files are gzipped because several of them exceed GitHub's 100 MB file limit
uncompressed; `gunzip` or `zcat` reads them, and pandas, R and awk all read
`.gz` directly. Ranks 7 to 11 are split into parts because they exceed the
limit even compressed; every part carries the same header, so concatenating the
parts after dropping the repeated header lines reconstitutes the rank.

| column | meaning |
|---|---|
| `rank` | the rank, proven |
| `conductor` | the conductor N, exact integer |
| `log_N` | log N |
| `naive_h` | naive height, log max(abs(c4)^3, c6^2) |
| `a_invs` | `[a1,a2,a3,a4,a6]` of the minimal model |
| `generators` | independent points generating a finite-index subgroup of rank many |

Points are given as `[x,y]` in the coordinates of the listed minimal model, and
**may have rational coordinates**: 50% of the curves here have at least one
generator with a denominator, and denominators reach 32 digits, so read them as
exact rationals. Likewise most of the conductors exceed 2^53, so read the
`conductor` column as an exact integer and not as a floating point number.

No curve appears twice, but a small number of the curves are isogenous to each
other, and isogenous curves share rank, conductor and L-function. In the range
published here that affects 28 curves, forming 14 isogenous pairs. To read a
curve in PARI/GP:

```
E = ellinit([a1,a2,a3,a4,a6]);
```

## Curves by torsion subgroup

The curves above with a nontrivial torsion subgroup are also collected by torsion
group under [`torsion/`](torsion/), one file per group, with the same columns plus
`torsion` (the group) and `torsion_generators` (points generating the torsion
subgroup, in the coordinates of the listed model). The torsion files are extracted
from the same master list as the rank files, which are refreshed less often, so a
curve can appear here before it appears in its `rank_r` file. The groups present so far:

| file | torsion | curves | ranks | smallest log N by rank |
|---|---|---:|---|---|
| `torsion/torsion_Z2.tsv.gz` | [Z/2](records/torsion_Z2.md) | 571,540 | 4 to 9 | [4: 40.969](records/torsion_Z2.md#rank-4), [5: 19.263](records/torsion_Z2.md#rank-5), [6: 24.529](records/torsion_Z2.md#rank-6), [7: 30.739](records/torsion_Z2.md#rank-7), [8: 36.438](records/torsion_Z2.md#rank-8), [9: 47.260](records/torsion_Z2.md#rank-9) |
| `torsion/torsion_Z3.tsv.gz` | [Z/3](records/torsion_Z3.md) | 3,040 | 4 to 8 | [4: 45.140](records/torsion_Z3.md#rank-4), [5: 22.840](records/torsion_Z3.md#rank-5), [6: 29.422](records/torsion_Z3.md#rank-6), [7: 36.860](records/torsion_Z3.md#rank-7), [8: 44.372](records/torsion_Z3.md#rank-8) |
| `torsion/torsion_Z2xZ2.tsv.gz` | [Z/2xZ/2](records/torsion_Z2xZ2.md) | 178 | 5 to 6 | [5: 24.168](records/torsion_Z2xZ2.md#rank-5), [6: 29.062](records/torsion_Z2xZ2.md#rank-6) |

Smallest log N in this collection by rank and torsion group:

| rank | Z/2 | Z/3 | Z/2xZ/2 |
|---:|---:|---:|---:|
| 4 | [40.969](records/torsion_Z2.md#rank-4) | [45.140](records/torsion_Z3.md#rank-4) |  |
| 5 | [19.263](records/torsion_Z2.md#rank-5) | [22.840](records/torsion_Z3.md#rank-5) | [24.168](records/torsion_Z2xZ2.md#rank-5) |
| 6 | [24.529](records/torsion_Z2.md#rank-6) | [29.422](records/torsion_Z3.md#rank-6) | [29.062](records/torsion_Z2xZ2.md#rank-6) |
| 7 | [30.739](records/torsion_Z2.md#rank-7) | [36.860](records/torsion_Z3.md#rank-7) |  |
| 8 | [36.438](records/torsion_Z2.md#rank-8) | [44.372](records/torsion_Z3.md#rank-8) |  |
| 9 | [47.260](records/torsion_Z2.md#rank-9) |  |  |

The search for curves with the other torsion groups (Z/4 to Z/12, Z/2xZ/4, Z/2xZ/6,
Z/2xZ/8) is in progress; their files will be added as curves are proven.

## Also here

`generators_scatterplots.pdf`, some notes on what the Mordell-Weil generators of
these curves look like when suitably normalized.

Github is giving me an error when trying to render the pdf, so please download it if you wish to see the scatterplots.

## Status

This is an ongoing computation, and the collection is being extended to higher
ranks. A description of how the curves were found will follow.

Michael Rubinstein, University of Waterloo
