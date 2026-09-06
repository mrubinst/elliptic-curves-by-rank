# Elliptic curves by rank

A collection of elliptic curves over **Q** of rank 4 to 14, given by minimal
Weierstrass model together with explicit Mordell-Weil generators.

Every curve here has **proven** rank. For each one the listed generators are
verified to lie on the curve and to be independent, which gives the rank as a
lower bound, and a 2-descent upper bound matches it. Every model is the minimal
model, and no curve appears twice.

## Contents

| file | rank | curves | smallest log N | smallest naive height | smallest Faltings height | smallest log abs(disc) |
|---|---:|---:|---:|---:|---:|---:|
| `rank_4.tsv.gz` | 4 | 577,645 | 12.364981 | 21.574288 | -0.173133 | 13.058128 |
| `rank_5.tsv.gz` | 5 | 410,002 | 16.762465 | 24.317973 | 0.083690 | 16.762465 |
| `rank_6.tsv.gz` | 6 | 517,766 | 22.369530 | 30.376041 | 0.582833 | 22.643449 |
| `rank_7.tsv.gz` | 7 | 551,603 | 26.670318 | 35.779031 | 1.036540 | 28.235073 |
| `rank_8.tsv.gz` | 8 | 674,348 | 33.151079 | 41.826383 | 1.524454 | 33.962016 |
| `rank_9.part1.tsv.gz`, `rank_9.part2.tsv.gz` | 9 | 1,038,230 | 38.007861 | 47.863736 | 1.982707 | 39.095558 |
| `rank_10.part1.tsv.gz` .. `rank_10.part3.tsv.gz` | 10 | 1,518,526 | 43.767868 | 54.348977 | 2.510505 | 45.376023 |
| `rank_11.part1.tsv.gz` .. `rank_11.part4.tsv.gz` | 11 | 1,560,638 | 51.246420 | 61.346666 | 3.041194 | 51.246420 |
| `rank_12.part1.tsv.gz`, `rank_12.part2.tsv.gz` | 12 | 468,891 | 57.764522 | 68.672711 | 3.722319 | 59.188359 |
| `rank_13.tsv.gz` | 13 | 23,017 | 64.738469 | 75.137429 | 4.245237 | 65.837081 |
| `rank_14.tsv.gz` | 14 | 301 | 74.077904 | 83.160631 | 4.987386 | 74.771051 |

7,340,967 curves in total.

The four minima in each row are taken independently over that rank, so they are
generally attained by four different curves. Heights are natural logarithms.
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
`.gz` directly. Ranks 9 to 12 are split into parts because they exceed the
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
**may have rational coordinates**: 48% of the curves here have at least one
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

## Also here

`generators_scatterplots.pdf`, some notes on what the Mordell-Weil generators of
these curves look like when suitably normalized.

Github is giving me an error when trying to render the pdf, so please download it if you wish to see the scatterplots.

## Status

This is an ongoing computation, and the collection is being extended to higher
ranks. A description of how the curves were found will follow.

Michael Rubinstein, University of Waterloo
