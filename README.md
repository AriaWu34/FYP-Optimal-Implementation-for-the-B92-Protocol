# Optimal Implementation for the B92 Protocol

This project investigates the optimal implementation of the **B92 quantum key distribution (QKD) protocol**. The goal is to determine the optimal non-orthogonal angle that maximises the secure key generation rate under varying noise conditions. The model assumes that all noise (error rate) originates from eavesdropping attacks and is evaluated against **collective** and **individual** attack models.

A detailed dissertation paper describing the algorithms and discussion of results is **available upon request**.

---

## Main Takeaway

**Key Results:**  
- **Max secure key rate (R)** for both attack types is approximately **0.50** at negligible noise (ε ≈ 0).
- **Cutoff noise threshold** (where R >= 0.1) is around **ε ≈ 0.1** for both attack types.
- Across the noise range:
  - **Individual attacks** consistently maintain slightly higher \( R \) than collective attacks for the same ε.
  - **Collective attacks** degrade faster as noise increases.
- The comparative notebook (`collective_vs_individual.ipynb`) visually illustrates this performance gap.

**Limitations:**  
These results are based on an **idealised model** that assumes:
- All noise originates from eavesdropping.
- Perfect photon sources, detectors, and channel alignment.
- No optical imperfections, dark counts, or channel loss.

Because of these assumptions, the reported secure key rates and cutoff noise thresholds are **overestimated** compared to real-world B92 implementations.

**Future Work:**  
- Incorporate realistic channel models with more parameters to be optimised.
- Extend analysis to other protocols (e.g., BB84) for benchmarking.

---

## How to Run

1. **Run attack simulations**  
   - Execute `b92_collective_attack.ipynb` to simulate the collective attack scenario.
   - Execute `b92_individual_attack.ipynb` to simulate the individual attack scenario.
   - Results and plots are generated within each notebook.

2. **Compare results**  
   - Run `collective_vs_individual.ipynb` to generate plots comparing collective and individual attack models.

3. **Experimental notebook**  
   - `b92_3states.ipynb` is a **work-in-progress** and serves as a framework for exploring a 3-state B92 variant.
  
---

## Data Files

- `collective_attack.csv` and `individual_attack.csv` contain **pre-generated results** used by `collective_vs_individual.ipynb` for comparison.
- Running the simulation notebooks with different parameters will **overwrite these files**.

---

## Requirements

Install Python 3.8+, Jupyter Notebook, and the following dependencies:

```bash
pip install numpy scipy matplotlib pandas sympy jupyter
