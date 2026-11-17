# Dynamic Quantumvengers: benchmarking noisy quantum hardware with dynamic circuits and error correction

This is a team project created for the IBM challenge of **QRISE 2024**, run by Quantum Coalition. The
team explored how dynamic circuits (mid-circuit measurement, reset and feed-forward),
quantum error-correction ideas and randomized techniques can be used to benchmark and protect quantum
operations on noisy hardware. All experiments use Qiskit simulators with noise models.

## Context and later work

- **Origin:** the project was created in April 2024 as the team's submission to the IBM challenge of
  QRISE 2024.
- **Poster:** it was later presented as a poster in Brno, Czech Republic, in 2025.
- **Follow-up projects:**
  - It is the predecessor of [low-cost-home-made-qc](https://github.com/hubertkolcz/low-cost-home-made-qc),
    a project on a low-cost, home-made quantum computer.
  - It is the conceptual basis of
    [Lie-Poisson geometric criteria for classical optical emulation in MBQC](https://github.com/hubertkolcz/Lie-Poisson-geometric-criteria-for-classical-optical-emulation-in-MBQC),
    a study prepared for the 46th Winter School Geometry and Physics (Srní, 2026). That repository
    includes this one as a submodule.

## Team

| Member | Contribution |
|---|---|
| [Hubert Kołcz](https://github.com/hubertkolcz) | The report *Increasing quantum operability with QECCs-tailored software tooling for hardware benchmarking*, plus the readout-error (bit-flip) experiment and two-qubit randomized benchmarking notebooks. |
| [Umi Yamaguchi](https://github.com/umi2004) | Static versus dynamic GHZ circuits: notebook and report. |
| [Ayeman Fatima](https://github.com/Ayeman985) | Quantum teleportation with randomized measurement and error correction: notebook and results report. |

## Contents

| File | Description |
|---|---|
| `QECCs - Hubert Kolcz.pdf` | Report on quantum error-correcting codes as a basis for hardware benchmarking. It covers Shor, surface, toric and QLDPC codes, existing tools (qiskit-qec, MQT QECC, Qiskit Experiments), and the two experiments below. |
| `QRISE_IBM_Project_bit-flip.ipynb` | A custom Qiskit Experiments experiment that compares direct and randomized (symmetrized) measurement under asymmetric readout error. |
| `QRISE_IBM_Project_2-qubit_exp.ipynb` | One- and two-qubit standard randomized benchmarking on a simulator with the FakePerth noise model. |
| `QRISE_IBM_Project_GHZ.ipynb` | Five-qubit static and dynamic GHZ circuits on a simulator with the FakeVigo noise model. |
| `QRISE-GHZ_Circuits_IBM_UmiYamaguchi.pdf` | Report: *Analysis of Static and Dynamic GHZ Circuits for Scalable Quantum Computing*. |
| `QRISE_FINAL_AYEMAN_FATIMA_.ipynb` | Teleportation in three cases (plain, Rx(5π/7) and Rx(2π/7)), with randomized measurement and a quantum-controlled error-correction circuit. |
| `RESULTS for Qrise Ayeman Fatima.docx` | Results report for the teleportation experiments. |
| `QRISE Video Presentation.mp4` | The team's video presentation. |

## Selected results (simulated)

- **GHZ states, 5 qubits** (from the GHZ report):
  - Static circuit: fidelity 98.76%, depth 6, 10 gates.
  - Dynamic circuit: fidelity 96.37%, depth 10, 19 gates.

  The static circuit reached higher fidelity. The report argues that the dynamic design is the more
  promising one for larger systems.
- **Teleportation** with readout error p(0|1) = 0.3 and p(1|0) = 0.05, across the three cases:
  - direct measurement: fidelity 0.50;
  - randomized measurement: 0.78–0.82;
  - error-correction circuit: 0.96–0.97.
- **Two-qubit randomized benchmarking** with the FakePerth noise model: error per Clifford
  0.0129 ± 0.0003 and error per CX gate 0.0070 ± 0.0004.

## Running the notebooks

The notebooks were written for Qiskit 1.0 (the saved outputs show Qiskit 1.0.2) and have not been
re-run since 2024. To set up a matching environment:

```bash
pip install "qiskit~=1.0" qiskit-aer qiskit-experiments qiskit-ibm-runtime pylatexenc matplotlib
```

Newer Qiskit releases may need small changes.

## Acknowledgements

- The randomized-measurement experiment follows the Qiskit Experiments tutorial
  [Writing your own experiment](https://qiskit-community.github.io/qiskit-experiments/tutorials/custom_experiment.html).
- The randomized benchmarking set-up follows the
  [Qiskit Experiments randomized benchmarking guide](https://qiskit-community.github.io/qiskit-experiments/manuals/verification/randomized_benchmarking.html).
- The dynamic GHZ circuit draws on the references listed in the GHZ report, including
  [arXiv:2308.13065](https://arxiv.org/abs/2308.13065).

## Licence

No licence has been chosen for this team project, so the files remain the property of their authors.
Please contact the team before reusing them.
