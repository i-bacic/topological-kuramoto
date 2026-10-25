# Krein Space, Exceptional Points, and PT Symmetry in the Topological Kuramoto Model

> **Status: Proposed extension / speculative framework.**
> Sections 1 and 2 cite published results. Section 3 is a well-motivated
> construction assembled from existing formalism that has not been written
> down for this model yet.

## 1. Exceptional Points and Kuramoto Multistability

A 2021 study of the PT-symmetric non-reciprocal Kuramoto model showed
explicitly that the two most unstable eigenvalues of the Jacobian L
coalesce at a critical coupling value j+ ≈ 0.007, and that this value
coincides with the transition from travelling waves to coherent states.

That coalescence IS an exceptional point (EP). At the EP, the Jacobian
becomes non-diagonalizable — the eigenvectors merge, and the system
enters a regime where the linearization breaks down.

### Connection to the ≥5 boundary rule

The Nature 2026 topological Kuramoto paper's "cascade of multistability"
works as follows:

- Each independent winding number (around a generalized cycle in the cell
  complex) is a discrete degree of freedom.
- When a boundary has < 5 elements, the winding numbers are constrained —
  only one admissible phase-locked state exists (the trivial one).
- At ≥ 5 elements, the winding numbers become independent — multiple
  distinct stable states coexist.

The transition from "constrained" to "independent" is structurally
identical to an EP: the eigenvalues of the stability matrix coalesce,
the system becomes non-diagonalizable, and a fan of stable states
emerges from a single point.

**Summary:** The EP is the LOCAL mechanism (eigenvalue coalescence →
non-diagonalizable Jacobian → fan of states). The ≥5 rule is the
TOPOLOGICAL condition (the cell complex has enough "room" for the
winding numbers to be independent). The EP is WHY multistability
appears; the boundary size is WHEN it is allowed to appear.

### The non-reciprocal connection

In the standard Kuramoto model, K_ij = K_ji (symmetric coupling), so
the Jacobian is "Hermitian" and you get a clean pitchfork bifurcation.
In the non-reciprocal model (K_ij ≠ K_ji), the Jacobian is
"non-Hermitian," and the pitchfork becomes an exceptional point — the
bifurcation is no longer a clean crossing but a coalescence. That is
the exact structural change that enables multistability.

## 2. Can PT Symmetry Explain Cosmological Winding Numbers?

**Short answer: it explains why they are STABLE, not why they have
the values they do.**

### Published results

- **Dai & Zhao (2026), arXiv:2601.19069:** PT symmetry generates
  winding numbers over O(2) ⊂ O(3) and O(2) ⊂ O(4). The winding number
  is a homotopy invariant defined by the fundamental group of the
  transition function. Key result: w^PT_{1,a1} = 0, w^PT_{1,a2} = 1,
  w^PT_2 = 1 — the PT structure SELECTS which winding sectors are
  non-trivial.

- **Non-Hermitian SSH model (arXiv:2509.09587, 2026):** Winding number
  Ω = (1/2π) ∫ ∂_k arg v_k. In the PT-symmetric region, Ω is a
  PROTECTED integer. In the PT-broken region, Ω fluctuates and is no
  longer quantized. The PT-breaking transition is itself a topological
  phase transition.

- **3D PT-symmetric topological phases (Phys Rev B, 2024):** The bulk
  invariant is the Pontryagin index — the same object as the BPST
  instanton number in Yang-Mills theory. This is an s³ winding number.
  Edge states are protected and can only be removed by non-Abelian
  braiding.

### What this means

The winding numbers in the topological Kuramoto model (phases winding
around generalized cycles in a cell complex) are structurally identical
to the winding numbers in PT-symmetric band theory (eigenvalues winding
around a reference energy in the complex plane). The math is the same:
a map from a cycle to a circle, classified by π¹(S¹) = ℤ.

PT symmetry provides the PROTECTION mechanism: the winding number can
only change if you (a) break PT symmetry, or (b) close a gap. In a
cosmological context:

- The winding numbers are topologically protected — they cannot decay
  or fluctuate as long as the PT structure is intact.
- The specific VALUE is set by initial conditions (the homotopy class
  at t=0).
- PT symmetry does not explain WHY the universe started with winding
  number 1 vs 2 vs 7. It explains why, once set, the value is ROBUST
  against perturbations.

**Honest status:** PT symmetry is a stability argument, not an origin
argument. For the origin, you would need a cosmological phase
transition (analogous to the PT-breaking transition) that set the
initial homotopy class.

## 3. The Krein Space Metric for Kuramoto (Proposed)

> **This section has not been published.** It is a natural construction
> that follows from the pieces, but nobody has written it down for the
> Kuramoto model specifically.

### The setup

The Kuramoto model has a natural energy landscape:

    H = -(K/2N) Σ_{i,j} sin(θ_j - θ_i) - Σ_i ω_i θ_i

The "states" are points on the torus T^N. The "dynamics" are gradient
flow on this landscape.

### The Hermitian case (standard Kuramoto)

When K_ij = K_ji (reciprocal), the coupling matrix is symmetric. The
Jacobian is "Hermitian" — real eigenvalues, complete eigenvector set.
The natural metric on T^N is positive-definite:

    [θ, φ] = Σ_i θ_i φ_i

Standard Hilbert space. No Krein space needed.

### The non-Hermitian case (non-reciprocal Kuramoto)

When K_ij ≠ K_ji, the coupling matrix is NOT symmetric. The Jacobian
can have complex eigenvalues and is NOT diagonalizable at exceptional
points. This is the "non-Hermitian" regime.

### The Krein space construction

1. **Define a fundamental symmetry J** (diagonal, ±1 entries) that
   encodes the PT structure:

       J = diag(1, 1, ..., 1, -1, -1, ..., -1)
              N_+ entries    N_- entries

   J partitions oscillators into P-even and P-odd sectors.

2. **The Krein metric** (indefinite inner product):

       [θ, φ]_K = (θ, Jφ) = Σ_{i=1}^{N_+} θ_i φ_i - Σ_{j=1}^{N_-} θ_j φ_j

   This can be positive, negative, or zero.

3. **The physical condition:** the Kuramoto "Hamiltonian" is
   J-self-adjoint (pseudo-Hermitian):

       H† J = J H

   This guarantees real spectrum in the unbroken PT phase and complex
   spectrum in the broken phase.

4. **At the exceptional point:** J becomes indefinite in a new way —
   the Krein positivization (replacing J with |J|) no longer gives a
   valid metric. The system is genuinely non-Hermitian.

### Connection to the ≥5 rule

The ≥5 boundary rule for multistability is, in this language, a
statement about the KREIN INDEX (the number of negative eigenvalues of
J):

- Boundary < 5 elements → Krein index is constrained (all positive, or
  at most one negative) → metric is "almost positive-definite" → one
  stable state.
- Boundary ≥ 5 elements → Krein index can be any value from 0 to N →
  metric is genuinely indefinite → multiple stable states coexist.

### The multistability cascade

The cascade of multistability across dimensions is the Krein index
PROPAGATING THROUGH THE CELL COMPLEX: winding numbers on 0-cells (nodes)
set the Krein index for 1-cells (edges), which sets it for 2-cells
(faces), etc. Each dimension inherits and modifies the Krein structure
of the one below.

### Status

This is a well-motivated construction. All individual pieces are
published. The specific assembly — "here is the Krein metric for the
topological Kuramoto model on a cell complex" — has not been written
down. A paper would be:

1. Define the cell complex and boundary/coboundary operators.
2. Define non-reciprocal coupling through B_n and B_{n+1}^T.
3. Construct J from the PT structure of the coupling.
4. Show the ≥5 rule is equivalent to a condition on the Krein index.
5. Show the multistability cascade is the propagation of the Krein
   index through dimensions.

Estimated: 4–6 page letter (PRL) or 10-page paper (PRE).   
