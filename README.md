# Elliptic curves by rank

A collection of elliptic curves over **Q** of rank 4 to 14, given by minimal
Weierstrass model together with explicit Mordell-Weil generators.

Every curve here has **proven** rank. For each one the listed generators are
verified to lie on the curve and to be independent, which gives the rank as a
lower bound, and a 2-descent upper bound matches it. Every model is the minimal
model, and no curve appears twice.

## Contents

| file | rank | curves | smallest conductor found |
|---|---:|---:|---:|
| `rank_4.tsv.gz` | 4 | 577,645 | log N = 12.364981 |
| `rank_5.tsv.gz` | 5 | 410,002 | log N = 16.762465 |
| `rank_6.tsv.gz` | 6 | 501,328 | log N = 22.369530 |
| `rank_7.tsv.gz` | 7 | 532,880 | log N = 26.670318 |
| `rank_8.tsv.gz` | 8 | 640,145 | log N = 33.151079 |
| `rank_9.part1.tsv.gz`, `rank_9.part2.tsv.gz` | 9 | 970,947 | log N = 38.007861 |
| `rank_10.part1.tsv.gz` .. `rank_10.part3.tsv.gz` | 10 | 1,459,139 | log N = 43.767868 |
| `rank_11.part1.tsv.gz`, `rank_11.part2.tsv.gz` | 11 | 950,245 | log N = 51.246420 |
| `rank_12.tsv.gz` | 12 | 96,780 | log N = 57.764522 |
| `rank_13.tsv.gz` | 13 | 1,687 | log N = 64.738469 |
| `rank_14.tsv.gz` | 14 | 33 | log N = 74.587110 |

6,140,831 curves in total.

## Format

Tab-separated, gzipped, one curve per line, sorted by ascending conductor.
The files are gzipped because several of them exceed GitHub's 100 MB file limit
uncompressed; `gunzip` or `zcat` reads them, and pandas, R and awk all read
`.gz` directly. Ranks 9, 10 and 11 are split into parts because they exceed the
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
may have rational coordinates. To read a curve in PARI/GP:

```
E = ellinit([a1,a2,a3,a4,a6]);
```

Conductors exceed 2^53 throughout most of the collection, so read the
`conductor` column as an exact integer rather than as a floating point number.

## Also here

`generators_scatterplots.pdf`, some notes on what the Mordell-Weil generators of
these curves look like when suitably normalized.

Github is giving me an error when trying to render the pdf, so please download it if you wish to see the scatterplots.

## Status

This is an ongoing computation, and the collection is being extended to higher
ranks. A description of how the curves were found will follow.

Michael Rubinstein, University of Waterloo
