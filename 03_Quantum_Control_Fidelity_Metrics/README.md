**03. Quantum Channel Analysis & Process Fidelity**

**Project Goal**

This project demonstrates expertise in the final stage of quantum computation analysis: Channel Fidelity Metrics. While Skill I dealt with states and Skill II dealt with dynamics, this project deals with the operations (gates) that transform states, and the necessary metrics to benchmark their quality in the presence of hardware noise.

The goal is to implement and compare two crucial quantum operations using their $\chi$ (Chi) matrix representation (the Quantum Process Matrix):

1. Ideal Process: The perfect two-qubit CNOT gate.

2. Noisy Process: The CNOT gate followed by a Depolarizing Channel (a model for gate-level error).

The key output is the Process Fidelity ($F_{pro}$), which mathematically quantifies how close the noisy operation is to the ideal operation.

**Relevance to Research Proposal**

This exercise is absolutely critical for the success of Objective 3 in your research proposal (Performance Benchmarking), and reinforces all engineering topics:

1. Topic 3 (QEC Code Design): The success of your new low-weight QEC code hinges on the fidelity of the CNOT gates (or their equivalents) used in the stabilizer circuits. This proof shows you know how to calculate that fidelity.

2. Topic 6 (QOC): Quantum Optimal Control aims to design pulses that achieve high Process Fidelity. This project proves you can calculate the metric used for optimization.

**Key Implementations**

1. Conversion of unitary operations ($U$) to the Quantum Process $\chi$ matrix.

2. Construction of a Depolarizing Noise Channel.

3. Calculation of Process Fidelity $F_{pro}$ (a measure of operational quality).

**Dependencies**

This project relies on the core qiskit.quantum_info module for its matrix and fidelity functions, ensuring the use of industry-standard tools.
