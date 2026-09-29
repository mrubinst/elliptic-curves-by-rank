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
| `rank_4.tsv.gz` | [4](records/rank_4.md) | 581,559 | [12.364981](records/rank_4.md#smallest-conductor) | [21.574288](records/rank_4.md#smallest-naive-height) | [-0.173133](records/rank_4.md#smallest-faltings-height) | [13.058128](records/rank_4.md#smallest-absolute-discriminant) |
| `rank_5.tsv.gz` | [5](records/rank_5.md) | 421,550 | [16.762465](records/rank_5.md#smallest-conductor) | [24.317973](records/rank_5.md#smallest-naive-height) | [0.083690](records/rank_5.md#smallest-faltings-height) | [16.762465](records/rank_5.md#smallest-absolute-discriminant) |
| `rank_6.part1.tsv.gz`, `rank_6.part2.tsv.gz` | [6](records/rank_6.md) | 1,396,828 | [22.369530](records/rank_6.md#smallest-conductor) | [30.376041](records/rank_6.md#smallest-naive-height) | [0.582833](records/rank_6.md#smallest-faltings-height) | [22.643449](records/rank_6.md#smallest-absolute-discriminant) |
| `rank_7.part1.tsv.gz` .. `rank_7.part4.tsv.gz` | [7](records/rank_7.md) | 3,681,098 | [26.670318](records/rank_7.md#smallest-conductor) | [35.779031](records/rank_7.md#smallest-naive-height) | [1.036540](records/rank_7.md#smallest-faltings-height) | [28.235073](records/rank_7.md#smallest-absolute-discriminant) |
| `rank_8.part1.tsv.gz` .. `rank_8.part4.tsv.gz` | [8](records/rank_8.md) | 2,883,871 | [33.151079](records/rank_8.md#smallest-conductor) | [41.826383](records/rank_8.md#smallest-naive-height) | [1.511528](records/rank_8.md#smallest-faltings-height) | [33.644948](records/rank_8.md#smallest-absolute-discriminant) |
| `rank_9.part1.tsv.gz` .. `rank_9.part5.tsv.gz` | [9](records/rank_9.md) | 3,301,005 | [38.007861](records/rank_9.md#smallest-conductor) | [47.863736](records/rank_9.md#smallest-naive-height) | [1.982707](records/rank_9.md#smallest-faltings-height) | [39.095558](records/rank_9.md#smallest-absolute-discriminant) |
| `rank_10.part1.tsv.gz` .. `rank_10.part4.tsv.gz` | [10](records/rank_10.md) | 1,665,924 | [43.767868](records/rank_10.md#smallest-conductor) | [54.348977](records/rank_10.md#smallest-naive-height) | [2.510505](records/rank_10.md#smallest-faltings-height) | [45.376023](records/rank_10.md#smallest-absolute-discriminant) |
| `rank_11.part1.tsv.gz` .. `rank_11.part6.tsv.gz` | [11](records/rank_11.md) | 2,268,936 | [51.246420](records/rank_11.md#smallest-conductor) | [61.185893](records/rank_11.md#smallest-naive-height) | [3.041194](records/rank_11.md#smallest-faltings-height) | [51.246420](records/rank_11.md#smallest-absolute-discriminant) |
| `rank_12.part1.tsv.gz`, `rank_12.part2.tsv.gz` | [12](records/rank_12.md) | 683,638 | [57.764522](records/rank_12.md#smallest-conductor) | [68.672711](records/rank_12.md#smallest-naive-height) | [3.722319](records/rank_12.md#smallest-faltings-height) | [59.188359](records/rank_12.md#smallest-absolute-discriminant) |
| `rank_13.tsv.gz` | [13](records/rank_13.md) | 59,552 | [64.738469](records/rank_13.md#smallest-conductor) | [75.137429](records/rank_13.md#smallest-naive-height) | [4.245237](records/rank_13.md#smallest-faltings-height) | [65.837081](records/rank_13.md#smallest-absolute-discriminant) |
| `rank_14.tsv.gz` | [14](records/rank_14.md) | 3,315 | [72.303161](records/rank_14.md#smallest-conductor) | [82.371945](records/rank_14.md#smallest-naive-height) | [4.863211](records/rank_14.md#smallest-faltings-height) | [73.720054](records/rank_14.md#smallest-absolute-discriminant) |
| `rank_15.tsv.gz` | [15](records/rank_15.md) | 26 | [81.565498](records/rank_15.md#smallest-conductor) | [92.182205](records/rank_15.md#smallest-naive-height) | [5.637976](records/rank_15.md#smallest-faltings-height) | [82.746402](records/rank_15.md#smallest-absolute-discriminant) |

16,947,302 curves in total.

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
**may have rational coordinates**: 32.5% of the curves here have at least one
generator with a denominator, and denominators reach 35 digits, so read them as
exact rationals. Likewise most of the conductors exceed 2^53, so read the
`conductor` column as an exact integer and not as a floating point number.

No curve appears twice, but some of the curves are isogenous to each other,
and isogenous curves share rank, conductor and L-function. In the range
published here there are 32,651 isogenous pairs, almost all of them at ranks 6
and 7. To read a
curve in PARI/GP:

```
E = ellinit([a1,a2,a3,a4,a6]);
```

## Curves by torsion subgroup

The curves above with a nontrivial torsion subgroup are also collected by torsion
group under [`torsion/`](torsion/), one file per group, with the same columns plus
`torsion` (the group) and `torsion_generators` (points generating the torsion
subgroup, in the coordinates of the listed model). Every curve in these files also
appears in its `rank_r` file. The groups present so far:

| file | torsion | curves | ranks | smallest log N by rank |
|---|---|---:|---|---|
| `torsion/torsion_Z2.tsv.gz` | [Z/2](records/torsion_Z2.md) | 644,993 | 4 to 9 | [4: 15.298](records/torsion_Z2.md#rank-4), [5: 19.263](records/torsion_Z2.md#rank-5), [6: 24.529](records/torsion_Z2.md#rank-6), [7: 30.739](records/torsion_Z2.md#rank-7), [8: 36.438](records/torsion_Z2.md#rank-8), [9: 44.625](records/torsion_Z2.md#rank-9) |
| `torsion/torsion_Z3.tsv.gz` | [Z/3](records/torsion_Z3.md) | 7,177 | 4 to 9 | [4: 16.239](records/torsion_Z3.md#rank-4), [5: 21.625](records/torsion_Z3.md#rank-5), [6: 26.966](records/torsion_Z3.md#rank-6), [7: 36.085](records/torsion_Z3.md#rank-7), [8: 42.561](records/torsion_Z3.md#rank-8), [9: 61.899](records/torsion_Z3.md#rank-9) |
| `torsion/torsion_Z4.tsv.gz` | [Z/4](records/torsion_Z4.md) | 4,314 | 4 to 6 | [4: 17.737](records/torsion_Z4.md#rank-4), [5: 22.184](records/torsion_Z4.md#rank-5), [6: 29.901](records/torsion_Z4.md#rank-6) |
| `torsion/torsion_Z5.tsv.gz` | [Z/5](records/torsion_Z5.md) | 2,156 | 4 to 6 | [4: 21.613](records/torsion_Z5.md#rank-4), [5: 29.021](records/torsion_Z5.md#rank-5), [6: 36.471](records/torsion_Z5.md#rank-6) |
| `torsion/torsion_Z6.tsv.gz` | [Z/6](records/torsion_Z6.md) | 90 | 4 to 5 | [4: 19.975](records/torsion_Z6.md#rank-4), [5: 29.321](records/torsion_Z6.md#rank-5) |
| `torsion/torsion_Z7.tsv.gz` | [Z/7](records/torsion_Z7.md) | 8 | 4 to 4 | [4: 29.804](records/torsion_Z7.md#rank-4) |
| `torsion/torsion_Z8.tsv.gz` | [Z/8](records/torsion_Z8.md) | 21 | 4 to 4 | [4: 29.638](records/torsion_Z8.md#rank-4) |
| `torsion/torsion_Z2xZ2.tsv.gz` | [Z/2xZ/2](records/torsion_Z2xZ2.md) | 210 | 5 to 6 | [5: 22.340](records/torsion_Z2xZ2.md#rank-5), [6: 29.049](records/torsion_Z2xZ2.md#rank-6) |
| `torsion/torsion_Z4xZ2.tsv.gz` | [Z/4xZ/2](records/torsion_Z4xZ2.md) | 2 | 4 to 4 | [4: 22.553](records/torsion_Z4xZ2.md#rank-4) |
| `torsion/torsion_Z6xZ2.tsv.gz` | [Z/6xZ/2](records/torsion_Z6xZ2.md) | 25 | 4 to 4 | [4: 31.586](records/torsion_Z6xZ2.md#rank-4) |

Smallest log N in this collection by rank and torsion group:

| rank | Z/2 | Z/3 | Z/4 | Z/5 | Z/6 | Z/7 | Z/8 | Z/2xZ/2 | Z/4xZ/2 | Z/6xZ/2 |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 4 | [15.298](records/torsion_Z2.md#rank-4) | [16.239](records/torsion_Z3.md#rank-4) | [17.737](records/torsion_Z4.md#rank-4) | [21.613](records/torsion_Z5.md#rank-4) | [19.975](records/torsion_Z6.md#rank-4) | [29.804](records/torsion_Z7.md#rank-4) | [29.638](records/torsion_Z8.md#rank-4) |  | [22.553](records/torsion_Z4xZ2.md#rank-4) | [31.586](records/torsion_Z6xZ2.md#rank-4) |
| 5 | [19.263](records/torsion_Z2.md#rank-5) | [21.625](records/torsion_Z3.md#rank-5) | [22.184](records/torsion_Z4.md#rank-5) | [29.021](records/torsion_Z5.md#rank-5) | [29.321](records/torsion_Z6.md#rank-5) |  |  | [22.340](records/torsion_Z2xZ2.md#rank-5) |  |  |
| 6 | [24.529](records/torsion_Z2.md#rank-6) | [26.966](records/torsion_Z3.md#rank-6) | [29.901](records/torsion_Z4.md#rank-6) | [36.471](records/torsion_Z5.md#rank-6) |  |  |  | [29.049](records/torsion_Z2xZ2.md#rank-6) |  |  |
| 7 | [30.739](records/torsion_Z2.md#rank-7) | [36.085](records/torsion_Z3.md#rank-7) |  |  |  |  |  |  |  |  |
| 8 | [36.438](records/torsion_Z2.md#rank-8) | [42.561](records/torsion_Z3.md#rank-8) |  |  |  |  |  |  |  |  |
| 9 | [44.625](records/torsion_Z2.md#rank-9) | [61.899](records/torsion_Z3.md#rank-9) |  |  |  |  |  |  |  |  |

The search for curves with the other torsion groups (Z/4 to Z/12, Z/2xZ/4, Z/2xZ/6,
Z/2xZ/8) is in progress; their files will be added as curves are proven.

## Curves from parametrized families

The directory [`families/`](families/) holds curves obtained by specializing parametrized families
of elliptic curves (elliptic surfaces over Q(t)), kept separate from the `rank_r` and `torsion` files.
A curve is included only when its rank is larger than the generic rank of the family it comes from.
There is one file per torsion subgroup (split into parts where needed), with the same columns as the
torsion files; for trivial torsion `torsion_generators` is `[]`. As everywhere in this repository,
every curve has proven rank, is given by its global minimal model, and appears once.

| file | torsion | curves | ranks | smallest log N by rank |
|---|---|---:|---|---|
| `families/family_trivial.tsv.gz` | [trivial](records/family_trivial.md) | 134 | 13 to 21 | [13: 77.797](records/family_trivial.md#rank-13), [14: 86.302](records/family_trivial.md#rank-14), [15: 96.221](records/family_trivial.md#rank-15), [16: 107.477](records/family_trivial.md#rank-16), [17: 119.205](records/family_trivial.md#rank-17), [18: 121.679](records/family_trivial.md#rank-18), [19: 137.182](records/family_trivial.md#rank-19), [20: 145.331](records/family_trivial.md#rank-20), [21: 166.030](records/family_trivial.md#rank-21) |
| `families/family_Z2.part1.tsv.gz` .. `family_Z2.part11.tsv.gz` | [Z/2](records/family_Z2.md) | 1,755,871 | 10 to 17 | [10: 56.173](records/family_Z2.md#rank-10), [11: 65.938](records/family_Z2.md#rank-11), [12: 74.055](records/family_Z2.md#rank-12), [13: 85.035](records/family_Z2.md#rank-13), [14: 95.519](records/family_Z2.md#rank-14), [15: 101.026](records/family_Z2.md#rank-15), [16: 131.966](records/family_Z2.md#rank-16), [17: 146.353](records/family_Z2.md#rank-17) |
| `families/family_Z4.part1.tsv.gz` .. `family_Z4.part2.tsv.gz` | [Z/4](records/family_Z4.md) | 350,184 | 5 to 10 | [5: 24.649](records/family_Z4.md#rank-5), [6: 32.690](records/family_Z4.md#rank-6), [7: 40.747](records/family_Z4.md#rank-7), [8: 48.168](records/family_Z4.md#rank-8), [9: 61.548](records/family_Z4.md#rank-9), [10: 78.506](records/family_Z4.md#rank-10) |
| `families/family_Z5.tsv.gz` | [Z/5](records/family_Z5.md) | 18 | 4 to 4 | [4: 22.139](records/family_Z5.md#rank-4) |
| `families/family_Z6.tsv.gz` | [Z/6](records/family_Z6.md) | 15 | 4 to 5 | [4: 22.973](records/family_Z6.md#rank-4), [5: 30.341](records/family_Z6.md#rank-5) |

## Also here

`generators_scatterplots.pdf`, some notes on what the Mordell-Weil generators of
these curves look like when suitably normalized.

Github is giving me an error when trying to render the pdf, so please download it if you wish to see the scatterplots.

## Status

This is an ongoing computation, and the collection is being extended to higher
ranks. A description of how the curves were found will follow.

Michael Rubinstein, University of Waterloo
