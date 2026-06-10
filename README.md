# ⚛️ Nanostructure Simulations and Quantum Mechanics

This repository contains the computational solutions developed for the Advanced Quantum Mechanics Laboratory. The project numerically explores two fundamental phenomena of quantum mechanics applied to solid-state devices: resonant tunneling in heterostructures and the quantization of electronic orbits (Landau levels) under magnetic fields.

## 🎯 The Challenge

The main challenge consisted in computationally modeling complex quantum systems, starting from the principles of the Schrödinger equation, to observe non-intuitive behaviors of matter:

- **Resonant Tunneling Effect:** Calculating the transmission coefficient of an electron through a double-barrier potential. We had to numerically demonstrate how the transmission probability reaches perfect unity when the electron's energy matches the quantum states of the well, and how this resonance is affected by introducing asymmetries or external biases.
- **Landau Levels:** Simulating the motion of an electron orbiting under a stationary magnetic field. Using the Landau gauge, the problem maps into a displaced quantum harmonic oscillator. The big challenge was computationally calculating highly excited states to visualize the convergence between quantum mechanics and classical physics.

## 🚀 Numerical Implementation

We developed algorithms focused on computational stability and physical fidelity, avoiding "black-box" simulators:

### 1. Transmission Dynamics (GaAs/GaAlAs Double Barrier)
We implemented the transmission coefficient modeling using the electron's effective mass (0.067 me) for both the GaAs wells and the GaAlAs barriers.

* **The Symmetric Case:** We located the exact resonance energies for a theoretical structure with 1 eV barriers.
* **The Asymmetric (Structural) Case:** We computed the system by confronting the electron with unequal barriers (0.5 eV vs. 1.13 eV), evaluating the degradation of the tunneling effect.
* **External Bias (Applied Field):** We modeled a uniform electric field along the structure, introducing a potential drop of -0.63 eV in the right barrier relative to the left one, thus simulating the operating conditions of a real tunneling diode.

### 2. Recursive Generation of Landau States
To avoid memory overflow and the instability involved in calculating factorials or massive Hermite polynomials from scratch, we designed an iterative approach:

* **Recurrence Algorithm:** We used the wavefunctions of the ground state and the first excited state as mathematical seeds. From there, we applied a robust recurrence relation to sequentially generate higher-index states.
* **The Classical Limit:** We successfully computed and plotted the wavefunction and the extreme probability density for the levels n=18, n=50, and n=100.

## 🛠️ Technologies Used

* **Python:** As the main engine for numerical resolution, spatial iteration, and recurrence management.
* **NumPy:** For massive vectorization of wavefunctions over thousands of spatial points and complex number computation.
* **Matplotlib:** Creation of advanced graphical visualizations to interpret probability densities and transmission spectra.

## 🏆 Key Achievements

- **Demonstration of the Correspondence Principle:** In the simulation of the Landau level n=100, it is perfectly observed how the quantum probability density "mimics" the classical one, accumulating the highest probability at the turning points (the edges of the oscillator), validating the physical theory at a numerical level.
- **Solver Flexibility:** The transmission code is capable of resolving any arbitrary potential profile, assimilating abrupt jumps or continuous gradients (such as those introduced by the electric bias).

> *Lab assignments developed for the Advanced Quantum Mechanics Laboratory - UC3M Physics Department.*

