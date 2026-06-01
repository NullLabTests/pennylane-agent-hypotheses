<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/sticker.svg">
    <img src="assets/sticker.svg" alt="PennyLane Agent Hypotheses" width="180"/>
  </picture>
</p>

<h1 align="center">PennyLane Agent Hypotheses</h1>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square" alt="License: MIT"></a>
  <a href="https://www.python.org/"><img src="https://img.shields.io/badge/Python-3.10+-blue.svg?style=flat-square" alt="Python 3.10+"></a>
  <a href="https://pennylane.ai"><img src="https://img.shields.io/badge/PennyLane-0.38+-teal.svg?style=flat-square" alt="PennyLane"></a>
  <a href="https://github.com/NullLabTests/pennylane-demos"><img src="https://img.shields.io/badge/Demos-fork-8B5CF6?style=flat-square" alt="Demos Fork"></a>
  <a href="https://github.com/NullLabTests/pennylane-agent-experiments"><img src="https://img.shields.io/badge/Experiments-runnable-00D4AA?style=flat-square" alt="Runnable Experiments"></a>
  <a href="#"><img src="https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square" alt="Status"></a>
</p>

<p align="center">
  <b>5 ranked, testable hypotheses</b> for agent-driven hybrid quantum/ML experiments using the <a href="https://pennylane.ai">PennyLane</a> demonstration suite.
</p>

---

## Overview

This repository defines the research agenda for a suite of agent-generated experiments exploring practical advantages in hybrid quantum-classical machine learning. Each hypothesis is grounded in recent theoretical results, references concrete PennyLane baselines, and specifies falsifiable metrics with estimated computational cost.

### Sister Repositories

| Repository | Purpose | Link |
|-----------|---------|------|
| **pennylane-demos** | Fork of PennyLaneAI/demos with Python implementations of each hypothesis | [→ View](https://github.com/NullLabTests/pennylane-demos) |
| **pennylane-agent-experiments** | Runnable Jupyter notebooks with configs, smoke tests & CI | [→ View](https://github.com/NullLabTests/pennylane-agent-experiments) |

---

## Hypotheses

| # | Title | Area | Est. Cost |
|---|-------|------|-----------|
| **H1** | Joint Classical–Quantum NAS for Pareto-Optimal HQNNs | Architecture Search | Medium |
| **H2** | Engineered Dissipation vs. Local Cost for BP Mitigation | Trainability | Medium |
| **H3** | Post-Variational Strategies on Non-Convex Landscapes | Expressivity / Cost | Low–Medium |
| **H4** | PDE-Constrained Loss Functions Suppress Gradient Vanishing | Trainability | Medium |
| **H5** | Data-Reuploading with Trainable Scaling on Small Benchmarks | Expressivity | Low–Medium |

Each hypothesis in [`hypotheses.json`](hypotheses.json) includes:
- **Description & rationale** — what is being tested and why
- **Novelty rationale** — how it differs from prior work
- **Expected metrics** — quantitative success criteria
- **Baseline notebook** — corresponding PennyLane demo
- **References** — supporting papers and resources

---

## Evaluation Metrics

| Metric | Description |
|--------|-------------|
| **Accuracy** | Test-set classification accuracy (% or AUROC) |
| **Gradient variance** | Variance of cost-function gradients across random initialisations (barren plateau severity) |
| **Convergence speed** | Epochs or wall-clock time to reach threshold loss |
| **FLOPs / parameter count** | Computational resource footprint at iso-accuracy |
| **Pareto hypervolume** | Multi-objective quality of discovered architectures |
| **Fraction barren** | Percentage of random initialisations resulting in untrainable landscapes |

---

## Quickstart

```bash
# Inspect the hypothesis definitions
cat hypotheses.json | python -m json.tool

# Run a baseline demo (e.g., H1 — Variational Classifier)
pip install pennylane
python -c "import pennylane as qml; print('PennyLane', qml.__version__)"
```

For executable experiments with notebooks and configs, visit the [pennylane-agent-experiments](https://github.com/NullLabTests/pennylane-agent-experiments) repo.

---

## Repository Structure

```
├── hypotheses.json      # 5 ranked hypotheses (JSON array, machine-readable)
├── README.md            # This file
├── LICENSE              # MIT License
└── assets/
    └── sticker.svg      # Project visual identity
```

---

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
