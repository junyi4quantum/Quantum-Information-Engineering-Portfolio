01. The Quantum Toolbox: State & Channel Representation

Project Goal

This project serves as a foundational proof of computational competence in Quantum Information Theory (QIT) by implementing and verifying the core mathematical objects used in modern quantum research.

Specifically, it demonstrates the ability to translate abstract quantum states (vectors) into their operational form (density matrices) and to perform the essential task of partial tracing—the mathematical tool used to discard irrelevant subsystems and calculate the state of a single component.

Relevance to Research Proposal

This exercise proves the theoretical prerequisite skills for nearly every topic, especially:

Topic 2 (Entanglement-Assisted ZNE): Calculating the partial trace is the first step in determining the reduced density matrix of a subsystem, which is required for calculating entanglement entropy and verifying the PTT (Peres-Horodecki) criterion.

Topic 6 (QIT-Informed Crosstalk Mitigation): The entire framework of QPT and noise modeling relies on the density matrix formalism ($\rho$).

Key Implementations

Conversion between State Vector ($|\psi\rangle$) and Density Matrix ($\rho$).

Calculation of the Partial Trace ($\text{Tr}_A \rho_{AB}$).

Verification of state purity using the Purity Index ($\text{Tr}(\rho^2)$).

Dependencies

This project uses standard Python libraries. Please ensure the environment is configured using the requirements.txt file.
