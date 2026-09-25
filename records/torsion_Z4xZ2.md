# Torsion Z/4xZ/2: record curves

The curves of this collection with torsion subgroup Z/4xZ/2, by rank: for each rank the
ten smallest conductors, with generators of the Mordell-Weil group and of the torsion
subgroup. Every curve has proven rank, is given by its global minimal model, and
appears in the corresponding `rank_r` file as well. Conductors are exact integers;
heights are natural logarithms; the naive height is `log max(abs(c4)^3, c6^2)`.

| rank | curves | smallest log N | smallest naive height | smallest log abs(disc) |
|---:|---:|---:|---:|---:|
| 4 | 2 | [22.553340](#rank-4) | 79.520692 | 67.501190 |

## Rank 4

| # | a-invariants | conductor N | log N | naive h | log abs(disc) | torsion generators |
|---:|---|---|---:|---:|---:|---|
| 1 | `[0,-1,0,-12528422340,539310754124100]` | **`6234348120`** | **22.553339859** | 81.367400000 | 67.50119043 | `[[41820,9407970],[63105,0]]` |
| 2 | `[1,0,0,-6769521299,122205015087249]` | **`39992228166`** | **24.411950976** | 79.520692000 | 71.67300828 | `[[-20480,15892777],[19078,-9539]]` |

<details><summary>generators for these ten</summary>

**1. `[0,-1,0,-12528422340,539310754124100]`**  N = 6234348120

```
E = ellinit([0,-1,0,-12528422340,539310754124100]);
generators:
  [107457,20828808]
  [1191785/16,281716435/64]
  [-108715,24827990]
  [4118845/36,5306617745/216]
torsion generators:
  [41820,9407970]
  [63105,0]
```

**2. `[1,0,0,-6769521299,122205015087249]`**  N = 39992228166

```
E = ellinit([1,0,0,-6769521299,122205015087249]);
generators:
  [18064,2402377]
  [96028,18863731]
  [-373451/16,1047483901/64]
  [2900806/9,4781862839/27]
torsion generators:
  [-20480,15892777]
  [19078,-9539]
```

</details>
