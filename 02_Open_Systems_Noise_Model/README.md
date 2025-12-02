**02. Lindblad Solver for Superconducting Qubit Dynamics**

**Project Goal**

This project demonstrates proficiency in modeling the time evolution of Open Quantum Systems using the Lindblad Master Equation. This is the fundamental theoretical tool for accurately simulating noise and decoherence—the primary challenge in NISQ (Noisy Intermediate-Scale Quantum) computing.

The goal is to simulate and plot the decay of a single qubit's excited state probability ($\langle \sigma_z \rangle$ expectation value) under the two dominant noise channels found in superconducting hardware:

1. Amplitude Damping ($T_1$): Energy relaxation from the excited state $|1\rangle$ to the ground state $|0\rangle$.

2. Phase Damping ($T_2$): Loss of phase coherence (pure dephasing).

**Relevance to Research Proposal**

This exercise proves the theoretical and computational prerequisite skills for the most advanced hardware-focused topics:

Topic 6 (QIT-Informed Crosstalk Mitigation / QOC): Any Quantum Optimal Control (QOC) pulse must be simulated under realistic Lindblad noise. This project proves the ability to set up the dynamics model needed for QOC optimization.

Topic 2 (Entanglement-Assisted ZNE): Understanding the exponential nature of $T_1$ and $T_2$ decay is necessary to formulate and benchmark effective error mitigation strategies like Zero-Noise Extrapolation (ZNE).

**Key Implementations**

Construction of the Hamiltonian ($H$) and the Lindblad Collapse Operators ($L_k$).

Numerical solution of the Lindblad Master Equation using QuTiP's mesolve.

Visualization of the decay curves for the excited state population $P_1(t)$.

**Dependencies**

This project requires QuTiP (Quantum Toolbox in Python) for the differential equation solver, in addition to standard numerical libraries.
