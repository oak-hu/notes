# A0 (Linear Algebra) — past-paper patterns & 2026 predictions

*Built from all 10 papers, 2016–2025 (Oxford Part A, paper A0), cross-checked against the current notes (Tillmann/Lauder/Dancer, Oct 2024) and the **official synopsis lecture weightings** ⟦n⟧. Companion files: `a0_heatmap.png` (topic × year), `a0_topic_matrix.csv`.*

---

## 0. TL;DR — what I'd bet on for 2026

1. **Format is rock-stable:** 3 questions, **best 2 count**, 1.5 hours. So you only need **two** questions — and you get to choose. Strategically you can prepare **two of the three pillars** thoroughly and still cover the paper.
2. **The three pillars never move:** every year the paper is built from (P) **canonical forms** — min/char poly, Cayley–Hamilton, primary decomposition, Jordan; (D) **dual spaces**; (I) **inner-product spaces** — forms, adjoints, spectral theorem, orthogonal/unitary. Usually one question per pillar (occasionally one pillar is split across two questions, or merged with another).
3. **Weight your revision by the synopsis:** the two ⟦3⟧ (heaviest) topics are **Primary Decomposition + Jordan** and **Dual spaces**. These are also the most-examined. They're your highest-yield revision.
4. **One genuinely new strand: the SVD.** It was *added to the notes in Oct 2024* (Nakatsukasa section), sits in the synopsis ⟦2⟧ line, and has **never been examined** (absent 2016–2025). Freshly-added, untested syllabus content is a classic target — I'd put real odds on **SVD appearing in 2026**, most likely as a part of the inner-product question.
5. **Recurring flavour to expect: char-p / finite-field twists** (2018, 2019, 2022, 2023, 2025) and **bilinear/sesquilinear forms** beyond the plain inner product (2021, 2025).

This paper is **proof-heavy and computation-light** — the only "computations" are small (find the min poly of a 3×3, compute a JNF, Gram–Schmidt a 2–3 element basis, write down an adjoint matrix). That suits a bookwork-strong, sustained-computation-averse style very well: A0 is almost all the thing you're good at.

---

## 1. The three pillars (and how they map to questions)

| Pillar | Topics | Synopsis weight | Appears |
|---|---|---|---|
| **P — Canonical forms** | min/char poly, Cayley–Hamilton, primary decomposition, Jordan, diagonalisability, quotients | ⟦1+2+3⟧ = **6 lec** (biggest) | every year, often **1–2 questions** |
| **D — Dual spaces** | dual basis, dual map = transpose, annihilators + dim formula, V≅V″, U⁰≅(V/U)′, rank T=rank T′ | ⟦3⟧ | most years, **a full question** |
| **I — Inner-product spaces** | forms (non-deg ⟺ V≅V′), Gram–Schmidt, adjoint, **spectral theorem**, orthogonal/unitary + groups, **SVD** | ⟦1+1+2⟧ = **4 lec** | every year, **a full question** |

The Q-number ↔ pillar mapping drifts (e.g. dual spaces was Q2 in 2016/2019/2020/2023 but Q3 in 2018, folded into Q1 in 2023/2025), so **don't memorise "Q2 = dual."** Prepare by *pillar*, not by question number.

---

## 2. ⭐ Bookwork ranked by likelihood (what to memorise)

A0 is bookwork-dominated, so this list *is* most of the exam. Ranked by frequency × synopsis weight.

### Tier 1 — near-certain, memorise the proof cold

| Result | Years asked | Synopsis | Note |
|---|---|---|---|
| **Min poly well-defined; p(A)=0 ⟺ m\|p; roots of m = roots of χ = eigenvalues** | 16,17,19,20,21,25 | ⟦1⟧ | The universal opener; one-line divide-and-remainder proof. |
| **Diagonalisable ⟺ m = product of distinct linear factors** | 16,19,20,22,24,25 | ⟦3⟧ | The single most-reused theorem; proof = Primary Decomposition. |
| **Primary Decomposition Theorem** (coprime split via Bézout) | 16,19,22,23,25 | ⟦3⟧ | Heaviest topic. Know the `as+bt=1 ⇒ projections` proof and the induction. |
| **Adjoint exists / unique / = conjugate-transpose in an ON basis** | 16,17,18,22,23,24 | ⟦1⟧ | Opens most inner-product questions. |
| **Annihilator dimension formula `dim U⁰ = dim V − dim U`** | 17,19,23,25 | ⟦3⟧ | Core dual-spaces bookwork. |

### Tier 2 — high; know the proof

| Result | Years | Synopsis |
|---|---|---|
| **Cayley–Hamilton (state & prove)** — triangularise over C̄, flag argument | 17, 22 | ⟦2⟧ |
| **Self-adjoint Spectral Theorem** — real eigenvalues + ON eigenbasis | 17, 18, 24 | ⟦2⟧ |
| **Jordan Normal Form** — existence (nilpotent ker-filtration) + computing a JNF from kernel dims | 16,21,22,23,24 | ⟦3⟧ |
| **Dual map = transpose `[T′]=[T]ᵀ`; `im T′=(ker T)⁰`; rank T = rank T′** | 16,17,18,19,20,23 | ⟦3⟧ |
| **Triangularisable ⟺ χ (equiv. m) splits into linear factors** | 16, 23 | ⟦2⟧ |

### Tier 3 — know it, lighter

- **V ≅ V″ natural iso** (16), **U⁰ ≅ (V/U)′** (17, and a named synopsis bullet) — quick, occasionally asked.
- **Orthogonal/unitary ⟺ preserves length; |λ|=1; groups Oₙ/SOₙ/Uₙ/SUₙ; real canonical form** (20, 25) — ⟦2⟧.
- **Non-degenerate bilinear/sesquilinear form ⟺ V≅V′** (21, 25) — the abstract-forms angle; ⟦1⟧.
- **D+N (Jordan–Chevalley)** (20), **positive operators / √** (18) — one-off but clean.

### Tier 4 — build-from-pieces, not quotable bookwork

- **Normal operators** (16, 19, 23): the slick spectral theorem for normal maps is **Appendix B / explicitly non-examinable** and **not in the synopsis**. But exam questions *construct* it from examinable tools (‖Tv‖=‖T*v‖, T-invariance of U⊥, primary decomposition), spelling out each step. Know the building blocks; don't expect to cite "the normal spectral theorem."

---

## 3. New / drifting content to watch (lower confidence, higher payoff)

- **⭐ SVD — the standout.** Added to the notes Oct 2024, in the synopsis ⟦2⟧, **never yet examined**. Newly-added bookwork is a prime target. Learn: statement `A=UΣV*`, the construction via the spectral theorem on the positive-semidefinite `A*A` (σᵢ=√λᵢ(A*A)), `rank=#σᵢ>0`, `σ₁=‖A‖_op`, and the polar decomposition corollary `A=UₚH`. Most likely a *part* of the inner-product question (built on the spectral theorem you already need).
- **Char-p / finite fields** (2018, 2019, 2022, 2023, **2025**): a recurring twist on the canonical-form pillar — minimal polynomials over 𝔽ₚ, `xᵖ−1`, Frobenius, diagonalisability failing/holding in characteristic p. Increasingly common; worth a focused look at how separability (m′=0) interacts with diagonalisability.
- **Abstract bilinear/sesquilinear forms** (2021, 2025): non-degenerate forms, V=W×W′, group actions preserving a form. The synopsis names "non-degenerate symmetric bilinear forms ⟺ V≅V′," so this is fair game beyond the standard inner product.

---

## 4. Strategy, given best-2-of-3 and a bookwork-strong style

- **Bank two pillars completely.** The safest pair is **Canonical forms (P) + Dual spaces (D)** — together they're ⟦6⟧+⟦3⟧ of synopsis weight, the two heaviest areas, and both are almost pure proof with only tiny computations. That alone is designed to cover ~2 questions most years.
- **Keep the inner-product pillar as your third** — it's where the new SVD and the spectral theorem live; a little more variety (forms, groups) but still proof-led.
- **Memorise cold (Tier 1):** min-poly facts, diagonalisability ⟺ distinct linear factors, Primary Decomposition, adjoint construction, annihilator dimension formula.
- **Learn the SVD now** even though it's never appeared — it's the highest expected-value "new" bet for 2026, and it's short.
- The computations that remain (min poly of a small matrix, a JNF, Gram–Schmidt, an adjoint matrix) are **bounded, mechanical, 5-minute** tasks — not the sustained marathons of the A2 contour integrals. This paper rewards exactly your strengths.

*Caveat: the format and three-pillar structure are extremely well-corroborated (10 consistent years). The SVD prediction rests on the "new untested syllabus content" heuristic plus the dated notes/synopsis — high expected value but inherently a single-shot bet; the char-p and forms flavours are trends, not guarantees.*
