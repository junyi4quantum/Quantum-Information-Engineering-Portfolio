# Quantum Galton Box Simulation

**Womanium Wiser 2025 Quantum Project**


**Goal.** A complete, reproducible implementation of *quantum Galton boards* (QGB) that:

1. Builds the $N$-layer Galton board circuit and verifies the **Gaussian/binomial** distribution.
2. Extends the sampler to match other targets on a one‑hot rail: **Exponential** and **Hadamard quantum walk**.
3. Adds a **hardware‑inspired noise model** and an **optimized version** that maximizes accuracy (lower TVD, better acceptance, deeper N).

The repo contains two Jupyter notebooks (no‑noise and noise+optimization), a 2‑page summary (paper review) and organized results.

---

## Repo layout

```
.
├── README.md                         ← you are here
├── quantum galton box paper.pdf      ← paper referenced in this work
├── Paper Summary.pdf                 ← project summary & design (assumed present)
├── Quantum Galton box (no noise).ipynb   ← ideal sampler + verification for all targets
├── QGB (noise).ipynb                      ← noise models, optimizations, TVD comparision
└── Results/
    ├── No noise/                        ← plots + TVD for ideal runs (binomial/exp/hadamard)
    ├── Noise/                        ← baseline-noise vs optimized-noise comparisons
```

> The notebooks are self‑contained and print exactly what’s saved in `Results/`.

---


## What each notebook does

### `Quantum Galton box (no noise).ipynb`

* **Builds the physical‑peg QGB**: a single reusable coin qubit routes a one‑hot “ball” across $N+1$ bins via `CSWAP` + a write‑back `CNOT`.
* **Gaussian/binomial target**: proves that repeated unbiased routing gives the binomial $B(N, 1/2)$, approaching a Gaussian for large $N$.
* **All‑to‑all sampler** (target matching): converts a target pmf $p_0, …, p_N$ into angles $\theta_k = 2\arcsin\sqrt{p_k/r_k}$ with tail mass $r_{k+1} = r_k - p_k$. Implements:

  * **Exponential** target.
  * **Hadamard quantum walk** target (coin‑walk amplitudes → position pmf on the right‑move count).
* **Verification**: overlays empirical vs. ideal, prints mean/var and **TVD**.

### `QGB (noise).ipynb`

* **Noise models** (device‑like): amplitude/phase damping, two‑qubit depolarizing, readout errors.
* **Optimizations**: scheduling (right→left cascade), angle biasing, gate cancellation, and re‑use of the coin to reduce depth.
* **Real hardware runner** (Qiskit Runtime **Sampler**, no sessions): automatically picks a feasible backend, transpiles, runs in shot chunks, **post‑selects one‑hot rows**, and compares to ideal.
* **Uncertainty**: bootstraps distance metrics (95% CIs) and writes everything to `Results/qgb_results.txt`.

---

## How to reproduce the deliverables

### A. General algorithm for any number of layers (Gaussian/binomial)

1. Pick $N$. Bins are indexed 0..N.
2. Initialize a **coin** qubit to $|0\rangle$, set bin 0 to $|1\rangle$ (one‑hot ball).
3. For each layer $\ell=0..N-1$:

   * Apply `RX(π/2)` (unbiased) to the coin.
   * **Right→Left cascade**: `CSWAP(coin, b_j, b_{j+1})` for `j = ℓ, …, 0`, then `CNOT(b_{j+1} → coin)` once per layer to write back.
4. Measure all bins; the histogram over the final bin index $k$ matches **Binomial** $B(N, 1/2)$.

Run this end‑to‑end in *`Quantum Galton box (no noise).ipynb`*. The notebook plots empirical vs. ideal and prints TVD.

### B. Modify to other targets (all‑to‑all sampler)

* Compute angles from the desired pmf $p$ using the tail rule above; reuse the same router with `RY(θ_k)` in place of `RX(π/2)`.
* Implemented targets:

  * **Exponential**: $p_k \propto e^{-\lambda k}$.
  * **Hadamard‑walk**: pmf from a discrete‑time Hadamard walk (coin amplitudes → marginal position distribution).

### C. Noise model and optimized implementation

* Simulates realistic noise ($T_1/T_2$, depolarizing, readout), then applies optimization passes:

  * Gate re‑ordering to minimize entangling depth per layer.
  * Write‑back minimization and angle tweaks ($a,b$ bias across layers).
  * Choice of transpiler options (SABRE layout/routing, `optimization_level=3`).

### D. Distances with uncertainty

* Metrics: **TVD**, **Hellinger**, **Jensen–Shannon distance**, **Wasserstein‑1** (1D), **Kolmogorov‑Smirnov**.
* Uncertainty: **bootstrap** over the integer outcomes (post‑selection) to provide **95% CIs**.
* All metrics for Ideal / Noise / Optimized are appended to `Results/qgb_results.txt`.

---


## What to look at first

1. **No‑noise notebook** → to see the clean Gaussian/Exponential/Hadamard outcomes and the angle‑synthesis logic.
2. **Noise notebook** → to see how TVD grows and how the optimized schedule/angles recover accuracy.
3. **`Results`** → a compact view of all runs with metrics and 95% CIs.

---

## Citing & prior art

* Primary reference in this repo: *Universal Statistical Simulator* (Carney & Varcoe), see `quantum galton box paper.pdf` in the root.
* We follow its **physical‑peg** construction and extend it with an **all‑to‑all target sampler** and hardware‑friendly routing.

---
