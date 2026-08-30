# Elliptic curves by rank

A collection of elliptic curves over **Q** of rank 4 to 14, given by minimal
Weierstrass model together with explicit Mordell-Weil generators.

Every curve here has proven rank. For each one the listed generators are
verified to lie on the curve and to be independent, which gives the rank as a
lower bound, and a 2-descent upper bound matches it. Every model is the minimal
model.

## Contents

| file | rank | curves | smallest conductor found |
|---|---:|---:|---:|
| `rank_4.tsv.gz` | 4 | 577,645 | log N = 12.3650 |
| `rank_5.tsv.gz` | 5 | 410,002 | log N = 16.7625 |
| `rank_6.tsv.gz` | 6 | 488,037 | log N = 22.3695 |
| `rank_7.tsv.gz` | 7 | 501,449 | log N = 26.6703 |
| `rank_8.tsv.gz` | 8 | 544,521 | log N = 33.1511 |
| `rank_9.tsv.gz` | 9 | 556,942 | log N = 38.0079 |
| `rank_10.tsv.gz` | 10 | 303,559 | log N = 43.7679 |
| `rank_11.tsv.gz` | 11 | 80,224 | log N = 51.2464 |
| `rank_12.tsv.gz` | 12 | 6,233 | log N = 57.7645 |
| `rank_13.tsv.gz` | 13 | 460 | log N = 64.7385 |
| `rank_14.tsv.gz` | 14 | 32 | log N = 74.5871 |

3,469,104 curves in total.

## Format

Tab-separated, gzipped, one curve per line, sorted by ascending conductor.
The files are gzipped because two of them exceed GitHub's 100 MB file limit
uncompressed; `gunzip` or `zcat` reads them, and pandas, R and awk all read
`.gz` directly.

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

## Also here

`generators_scatterplots.pdf`, some notes on what the Mordell-Weil generators of
these curves look like when normalized by the curve's own c4.

Github is giving me an error when trying to render the pdf, so please download it if you wish to read it.

## Status

This is an ongoing computation, and the collection is being extended to higher
ranks. A description of how the curves were found will follow.
