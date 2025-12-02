# Global Summer School 2025: Applied Quantum Computing

This repository contains the completed hands-on lab exercises from the Qiskit Global Summer School (QGSS) 2025.

The QGSS is an intensive, two-week program combining theoretical lectures with practical quantum programming challenges, covering fundamental quantum algorithms, quantum noise mitigation, and advanced applications in chemistry and error correction.



## 🚀 Key Skills Demonstrated

This project showcases expertise across the essential domains of NISQ (Noisy Intermediate-Scale Quantum) computing:



| Skill Area | Core Competencies | Relevant Labs |
| --- | --- | --- |
| **Quantum Programming & Execution** | Circuit construction, Transpilation, IBM Quantum Platform usage, Real Hardware execution (Lab 0). | Lab 0, Lab 1 |
| **Noise Mitigation & Optimization** | Hardware-aware transpilation, Optimal qubit layout finding, Zero Noise Extrapolation (ZNE), Error Mitigation. | Lab 2 |
| **Variational Algorithms** | Formulating Optimization Problems (Max-Cut) into Ising Hamiltonians, Quantum Approximate Optimization Algorithm (QAOA), Variational Quantum Eigensolver (VQE) concepts. | Lab 2, Lab 3 |
| **Quantum Chemistry** | Simulating Molecular Hamiltonians (e.g., $N_2$), Basis Set Approximation, Sample-based Quantum Diagonalization (SQD). | Lab 3 |
| **Quantum Error Correction (QEC)** | Stabilizer formalism, CSS codes (Steane Code), Advanced QEC architectures (Toric Code, QLDPC), Code distance and efficiency. | Lab 4 |

## 🧪 Completed Labs Overview

The five lab exercises cover a progression from basic quantum operations to state-of-the-art quantum code design.

| Lab | Title | Core Focus | Files (Notebooks) |
| --- | --- | --- | --- |
| **Lab 0** | Hello Quantum World! | Introduction to Qiskit, GHZ state generation, running on simulators and real hardware (Bonus). | `Lab 0.ipynb` |
| **Lab 1** | Recreating Famous Experiments | Quantum state preparation, Bell State creation, CHSH inequality verification (entanglement). | `Lab 1.ipynb` |
| **Lab 2** | Cutting through the Noise | QAOA for Max-Cut problem, Transpilation strategies (e.g., optimal layout), Error Mitigation (ZNE). | `Lab 2.ipynb` |
| **Lab 3** | The Power of 'good sampling' | Quantum Chemistry (Simulating $N_2$), Sample-based Quantum Diagonalization (SQD) for ground state energy. | `Lab 3.ipynb` |
| **Lab 4** | Quantum Error Correction | Classical and Quantum Error Correction (e.g., Steane Code), Stabilizer formalism, Design of advanced QLDPC/Toric codes. | `Lab 4.ipynb` |

## 🔬 Deep Dive: Technical Summary

For a detailed, technical breakdown of the mathematical formalism and implementation methodology used in these labs, please see the dedicated [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md) file.

| Tool | Purpose |
| --- | --- |
| Qiskit (v2.x) | Primary quantum programming SDK. |
| Qiskit Runtime | Used for executing circuits on simulated and real IBM Quantum hardware. |
| NumPy & Matplotlib | Numerical computing and result visualization. |
| qutip (Lab 3) | Used for specialized Lindblad Master Equation simulations (as seen in the companion materials). |

**Certification:** Completion of the Qiskit Global Summer School 2025 is certified by IBM Quantum.

