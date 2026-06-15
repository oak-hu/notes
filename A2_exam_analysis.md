# A2 (Metric Spaces & Complex Analysis) — past-paper patterns & 2026 predictions

*Built from all 12 papers, 2014–2025 (Oxford Part A, paper A2). Companion files: `a2_heatmap.png` (topic × year grid), `a2_topic_matrix.csv` (the raw matrix). Cross-checked against the current course notes (`CA_notes.txt`, `ms_index.html`).*

---

## 0. TL;DR — what I'd bet on for 2026

1. **The format has changed and the 2025 shape will repeat.** 2025 split into **Section A (Metric Spaces, Q1–3)** and **Section B (Complex Analysis, Q4–6)**, *best two from each*. This forces you to do 2 MS + 2 CA — you can **no longer skip Metric Spaces** (under the old "best 4 of 6 = 2 MS + 4 CA" you could). Treat MS and CA as **equally weighted**.
2. **Conformal mapping / Riemann Mapping / Schwarz as a CA question is gone.** It was a guaranteed Q6 every year 2014–2024, then vanished in 2025 — because it's **not in the current CA notes at all**. The Möbius/sphere/conformal material **migrated into Metric Spaces (Ch 11)** and now shows up as a *Section A* question (2025 Q3b). Don't revise it as complex analysis; revise it as metric-space/ℂ∞ material.
3. **Two genuinely new examinable strands** (first seen 2025, present in current notes / freshly added): **(a) differentiation in ℝⁿ** (directional derivatives, the Jacobian, "partials exist ≠ differentiable") in Section A; **(b) infinite products / Weierstrass / the π cot πz expansion / analytic continuation** flavour in Section B. Newly-added content tends to get **re-tested while it's fresh**.
4. **The spine that has never missed:** a **contour-integration computation** (Section B — every single year) and a **Cauchy–Riemann + branch-of-log** question. These are non-negotiable.

Confidence: high on (1) the rebalancing and (2) conformal-leaving-CA (corroborated by the notes, not just one paper); medium on the *exact* new-content topics recurring (only one data point, 2025).

---

## 1. The structural shift (this drives everything)

| Era | Years | Count rule | MS : CA | Conformal/Möbius |
|---|---|---|---|---|
| Classic | 2014–2019, 2021–2023 | best **4** of 6 | 2 MS + 4 CA (MS skippable) | CA Q6, every year |
| Transition | 2020 (Oct, COVID), 2024 | best **2** of 6 | 2 MS + 4 CA | still CA Q6 (2024) |
| **New regime** | **2025 →** | best **2 per Section** | **3 MS + 3 CA, balanced** | **moved to MS (ℂ∞ / Ch 11)** |

**Evidence it's a real syllabus revision, not one examiner's whim:**
- The current **CA notes contain zero** occurrences of "Möbius", "conformal", "Riemann mapping", "Schwarz" — yet these were examined *every year 2014–2024*. They've been cut from the CA course.
- The current **MS notes now include** differentiation in ℝⁿ (directional derivatives, Jacobian — heavily) **and** Ch 11 on ℂ∞/stereographic/Möbius/conformality. 2025 Section A Q3 tested exactly these.
- So the geometric-function-theory content didn't die — it **relocated from CA into MS**.

**Predicted 2026 skeleton** (each ≈25 marks, answer best 2 per section):

- **Section A — Metric Spaces**
  - A1: metrics / completeness / a "is this complete/compact?" zoo + one proof.
  - A2: connectedness & path-connectedness, or **contraction mapping** (+ an application).
  - A3: **differentiation in ℝⁿ** and/or **ℂ∞ / stereographic / Möbius** (the migrated geometry).
- **Section B — Complex Analysis**
  - B1: **Cauchy–Riemann + branch of log / cut-plane**, possibly harmonic.
  - B2: a **named-theorem** question — Liouville / Morera+uniform-limits / Identity / Casorati–Weierstrass — wrapped around CIF.
  - B3: **singularities + Residue Theorem + a contour integral** (and/or series summation via cot).

---

## 2. ⭐ Bookwork ranked by likelihood (the "what to memorise" list)

These are the **state-and-prove / prove-this** results. Ranked by frequency *weighted toward post-revision relevance*. Your instinct ("Liouville yes, Morera's *proof* maybe not") is basically right — see the note under each.

### Tier 1 — near-certain, **memorise the proof cold**

| Result | Years asked to *prove* | Why it's a lock |
|---|---|---|
| **Cauchy–Riemann equations (state & prove)** | 14,18,19,22,23,24 (6×) | The most-repeated CA bookwork; opens a Section-B question roughly every other year, usually bundled with a branch-of-log part. |
| **Contraction Mapping Theorem (+ variants)** | 14,16,18,19,22,24,25 (7×) | The MS workhorse. Know the full proof (Cauchy iterate → limit → uniqueness) *and* the standard twists: "fⁿ is a contraction ⇒ unique fixed point" (16), "at most one fixed point + an example with none" (22), application to an integral/ODE equation (25). |
| **Path-connected ⇒ connected** (and continuous image of connected/compact is connected/compact) | 15,17,19,20,21,24,25 (7×) | Tiny proofs, asked constantly, and now in a 3-question Section A you'll almost surely meet one. |
| **Liouville (state & prove via CIF)** | 18,19,21,25 (4×) | Asked to *prove* far more often than Morera. Often the lead-in to FTA. |
| **Contour integral of a real integral** (compute, fully justified) | **every year** | Not "bookwork" but 100% guaranteed in Section B. See §3 for the contour-type breakdown. |

### Tier 2 — high; **know the proof, expect it in some year**

| Result | Years | Note |
|---|---|---|
| **Identity Theorem (state & prove)** + "does a holo f with f(1/n)=… exist?" | 17,19,21,23 | The "f(1/n)" existence puzzles recur — practice the zeros-isolated argument. |
| **Compact ⇒ sequentially compact** | 16,23 (+defs 24,25) | Core named proof; definitions of compact/seq-compact/complete are asked almost every year. |
| **Classify isolated singularities** (removable/pole/essential) + **res(g/h)=g(a)/h′(a)** + **f′/f has residue = order** | sing: 14,18,19,20,21,23,24,25; res-formulae: 14,19,23,24 | Bread-and-butter of the residue question. The two little residue lemmas are quick proofs that recur. |
| **Removable-singularity thm (bounded ⇒ removable)** & **Casorati–Weierstrass (essential ⇒ dense)** | rem:19,23,25; C–W:19,23 | Short, elegant, and a favourite "prove this" pair. |
| **Möbius / circlines / 3-point transitivity / stereographic ℂ∞** *(now as Section A)* | geometry every year; ℂ∞ form 25 | Revise it as **metric-space** material now. "Möbius maps circlines to circlines", "unique Möbius sending 3 pts to 3 pts", and the ℂ∞ chordal-metric facts are the examinable cores. |
| **Differentiation in ℝⁿ: differentiable ⇒ continuous; partials exist ≠ differentiable** | 25 (new) | One data point but freshly on-syllabus → likely re-tested. Memorise the canonical counterexample (a function with both partials at 0 but not differentiable). |

### Tier 3 — moderate; understand it, lighter memorisation

- **Morera — *stated* often (14,16,17,20,25) but only *proved* once (16).** Know the statement and how it gives "uniform limit of holomorphic is holomorphic" (asked 14,16,17,20,22); you rarely need to reproduce Morera's own proof. *(This is exactly your "not Morera's" intuition.)*
- **FTA / polynomial root bounds** (15,24) — short, comes via Liouville.
- **Laurent's theorem** — *stated/used* a lot (14,17,19,20,21,22) but essentially **never asked to prove** (you may quote it). Practise *computing* Laurent series instead.
- **Residue Theorem** — *stated* most years (14,15,16,19,20,25), almost never proved. Quote-and-use.
- **Argument principle / counting zeros** (19,24) and **Rouché** (24) — know N = 1/2πi ∮ f′/f and the "count zeros in a quadrant" technique; lower frequency.
- **Uniform continuity on a compact set** (21,22), **EVT** (15,20), **total boundedness** (22), **equivalent metrics** (19,20,21,22) — recurring as *parts* of larger MS questions.

### Tier 4 — low priority / safe to deprioritise

- **The old CA conformal-mapping question** (construct a conformal bijection between awkward regions; Riemann Mapping Theorem; Schwarz lemma). **Dropped from the CA syllabus** — do **not** spend Section-B revision time here. (The *Möbius/ℂ∞* sliver survives in Section A; the heavy region-mapping does not.)
- **Bessel functions / exotic generating-function integrals** (14,20) — appeared, but niche.

---

## 3. The contour-integration question (Section B, guaranteed) — know every contour

Every year has at least one. The recurring contour *types*, so you can drill the toolkit rather than memorise integrals:

| Contour / method | Years | Typical integrand |
|---|---|---|
| **Keyhole (branch cut / log)** | 17,19,20,21,22,25 | ∫₀^∞ xᵗ/…, ∫ ln x/…, ∫ ∛x/(1+x)² |
| **Semicircle + indentation** (pole on axis) | 17,18,21,23 | ∫ sin ax sin bx /x², ∫ (1−cos)/x² |
| **Sector** (e²ᵖⁱ/ⁿ wedge) | 23,24 | ∫₀^∞ dx/(1+xⁿ), ∫ x/(1+x³) |
| **Rectangle** | 15 | sinh/cosh integrands |
| **Trig ∫₀^{2π} dθ** (z=e^{iθ}) | 19,22 | ∫ dθ/(1−2p cosθ+p²) |
| **Summation via π cot πz / π coth** (Γ_N squares) | 14,16,18,24,25 | Σ 1/n², Σ coth(nπ)/n³, Σ 1/k^{2n} |

**Prediction:** at least one keyhole/branch integral **and** likely one series-summation-via-cotangent (it's appeared in 2024 *and* 2025 — momentum). Have the "estimate the big arc / small arc → 0" lemmas ready to cite.

---

## 4. New / drifting content to watch (lower confidence, higher payoff if it lands)

2025's Section B reached past the core notes into:
- **Mittag-Leffler-style expansion** π cot πz = 1/z + Σ(1/(z−n)+1/n) (2025 Q5b) — *built from removable singularities + Liouville on the difference*; the bounded-h′ ⇒ constant trick is very learnable and is **the same Liouville muscle** as Tier 1.
- **Weierstrass product for sin** (2025 Q5c) and the **Gamma function** as a holomorphic integral with analytic continuation + Γ(z+1)=zΓ(z) (2025 Q6) — these are **not in the core notes I have**. ⚠️ **Check your problem sheets / lecture updates**: if your course covered infinite products / Γ, treat them as fair game (they were just examined); if not, they may have been a one-off stretch by the 2025 examiner.

The reliably-learnable new strand is **differentiation in ℝⁿ** (Section A) — it's squarely in your MS notes, so prioritise it over the products/Γ material unless your sheets say otherwise.

---

## 5. How to spend revision time (given the above)

- **Stop** rehearsing region-by-region conformal maps and Riemann Mapping / Schwarz as CA — reclaim that time.
- **Start** treating Metric Spaces as half the exam: nail CMT + connectedness proofs + the completeness/compactness zoo, **and** the new differentiation-in-ℝⁿ + ℂ∞/Möbius Section-A material.
- **Memorise cold:** CR equations, Contraction Mapping Theorem, path-conn⇒conn / continuous-image lemmas, Liouville. (Tier 1.)
- **Drill, don't memorise:** the contour-integral toolkit (every contour type above), Laurent-series computation, singularity classification.
- **Know the statement, skip the proof:** Morera, Laurent, Residue Theorem, Riemann Mapping (the last is gone anyway).

*Caveat: predictions are pattern-extrapolation from 12 papers + the current notes. The format/migration calls are well-corroborated; the precise new-content recurrence (Γ, products) rests on a single year — verify against your problem sheets and any lecturer guidance.*
