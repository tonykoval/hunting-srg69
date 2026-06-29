# Hunting SRG(69)

**Does a strongly regular graph on (69, 20, 7, 5) exist?**

An interactive book documenting the hunt to settle the **smallest open
existence question** in the strongly-regular-graph tables. Unlike its
sister volume [*Hunting SRG(37)*](https://github.com/tonykoval/hunting-srg37)
— which asks whether a known *catalog* is complete — this one asks a
sharper question: is there **even one** graph with these parameters?

Brouwer's table marks `(69,20,7,5)` with a bare **?**. The parameters pass
every feasibility test (integral spectrum `{20, 5²³, (−3)⁴⁵}`, Krein,
absolute bound, …) yet no graph has been built and no non-existence proof
is known. Two neighbours were recently resolved — `SRG(65,32,15,16)`
*constructed* (Gritsenko 2021), `SRG(85,14,3,2)` *refuted* (Shpectorov–Zhao
2025) — leaving this as the smallest door still closed.

## What the hunt has proven

Every result below is an exhaustive computation that ended in a real
certificate, not a timeout (see Appendix B):

- **No automorphism of order 3, 5, or any prime ≥ 7** — orbit-matrix
  enumeration, `0` matrices in every case.
- **No automorphism of order 23** — prescribed-ℤ₂₃ SAT, UNSAT in 23 s.
- **No Cayley graph** — the only group of order 69 is ℤ₆₉, and it carries
  no partial difference set.

So any `SRG(69,20,7,5)`, if it exists, is a 2-group-symmetric or fully
rigid graph. The two remaining regions — the `p=2` involution sweep
(billions of orbit-matrix cubes) and the rigid Gram-PSD enumeration — are
cluster-scale, and either a witness (existence) or full exhaustion
(non-existence) settles the question.

## Read it

Open **`index.html`** in any modern browser — plain static assets, no
build step. Math renders with KaTeX; the automorphism sweep is a
filterable interactive table. Chapters:

| Part | Chapters |
|------|----------|
| **I — The Target** | 1. The Target · 2. The Orbit-Matrix Reduction |
| **II — The Hunt** | 3. The Automorphism Sweep · 4. Cayley &amp; the Asymmetric Wall |
| **III — Findings &amp; Frontier** | 5. Findings &amp; the Decision |
| **Appendices** | A. Notation · B. Theorems &amp; Proofs · C. Bibliography |

## Print to PDF

```
python scripts/build_print.py     # writes print_full.html
```
then open `print_full.html` and print to PDF.

## Companion code

The orbit-matrix enumerator, lifter, PDS search and Gram-PSD filter live in
[github.com/tonykoval/orbit-gen](https://github.com/tonykoval/orbit-gen);
this book is its hunt log for the (69,20,7,5) target.

## Licence

Content CC-BY-4.0; code MIT.
