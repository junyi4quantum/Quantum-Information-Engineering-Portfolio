**01. The Quantum Toolbox: State & Channel Representation**
**Project Goal**
This project serves as a foundational proof of computational competence in Quantum Information Theory (QIT) by implementing and verifying the core mathematical objects used in modern quantum research.

Specifically, it demonstrates the ability to translate abstract quantum states (vectors) into their operational form (density matrices) and to perform the essential task of partial tracing—the mathematical tool used to discard irrelevant subsystems and calculate the state of a single component.


**Key Implementations**
Conversion between State Vector |ψ⟩ and Density Matrix ρ.

**Mathematical Definition**: $\rho = |\psi\rangle\langle\psi|$

Calculation of the Partial Trace (Tr_A ρ_AB).

**Goal**: Compute the reduced state of subsystem B after tracing out subsystem A.

Verification of state purity using the Purity Index.

**Mathematical Definition**: Purity = Tr(ρ²). (A pure state has Purity = 1).

**Dependencies**
This project uses standard Python libraries. Please ensure the environment is configured using the requirements.txt file.
