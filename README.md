# Hunting SRG(69)

**Does a strongly regular graph on (69, 20, 7, 5) exist?**

An interactive book documenting the hunt to settle what was the **smallest
open existence question** in the strongly-regular-graph tables.

> **Status (2026-09-26): settled. There is no SRG(69,20,7,5).** Hence there
> is also no quasi-symmetric 2-(46,16,8) design with intersection numbers
> 4 and 6. The proof is computer-assisted and assumes no symmetry: the
> vertices become norm-4 vectors of an even lattice of rank 24, every
> possible host lattice is listed (the Niemeier lattices, and one genus of
> determinant 8 built from Borcherds' 665 lattices), and the last six cases
> are shown infeasible by two independent engines (CP-SAT; CNF/kissat with
> DRAT proofs checked by drat-trim). Two independent audits and a review of
> the write-up. The write-up (`docs/paper/srg69.tex` in
> [orbit-gen](https://github.com/tonykoval/orbit-gen)) is being prepared for
> review by a mathematician; it has not been published or peer-reviewed.
> Outline: **Chapter 7 — The End of the Hunt**. Unlike its
sister volume [*Hunting SRG(37)*](https://github.com/tonykoval/hunting-srg37)
— which asks whether a known *catalog* is complete — this one asks a
sharper question: is there **even one** graph with these parameters?

When the hunt began, Brouwer's table marked `(69,20,7,5)` with a bare **?**.
The parameters pass every standard feasibility test (integral spectrum
`{20, 5²³, (−3)⁴⁵}`, Krein, absolute bound, …), yet no graph had been built
and no non-existence proof was known. Two neighbours were recently resolved — `SRG(65,32,15,16)`
*constructed* (Gritsenko 2021), `SRG(85,14,3,2)` *refuted* (Shpectorov–Zhao
2025) — leaving this as the smallest door still closed.

## What the hunt proved before the ending (historical)

Chapters 1–6 were written while the question was open; the results below
are now consequences of the nonexistence theorem and are kept as the
record of the hunt.

Every result below is an exhaustive computation that ended in a real
certificate, not a timeout (see Appendix B):

- **No automorphism of order 5, or any prime ≥ 7** — orbit-matrix
  enumeration, `0` matrices in every case (largely re-verifying
  Behbahani–Lam). The order-3 case was later downgraded to a re-derivation
  in progress (Chapter 3); it was never finished and is no longer needed.
- **No automorphism of order 23** — prescribed-ℤ₂₃ SAT, UNSAT in 23 s.
- **No Cayley graph** — the only group of order 69 is ℤ₆₉, and it carries
  no partial difference set.

At that point the two remaining regions — the `p=2` involution sweep
(billions of orbit-matrix cubes) and the rigid Gram-PSD enumeration — were
cluster-scale. Neither was finished: the lattice proof of Chapter 7 settled
the question without them.

## Read it

Open **`index.html`** in any modern browser — plain static assets, no
build step. Math renders with KaTeX; the automorphism sweep is a
filterable interactive table. Chapters:

| Part | Chapters |
|------|----------|
| **I — The Target** | 1. The Target · 2. The Orbit-Matrix Reduction |
| **II — The Hunt** | 3. The Automorphism Sweep · 4. Cayley &amp; the Asymmetric Wall |
| **III — Findings &amp; Frontier** | 5. Findings &amp; the Decision · 6. Tools &amp; Reproducibility · 7. The End of the Hunt |
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
