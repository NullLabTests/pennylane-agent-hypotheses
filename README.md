# PennyLane Agent Hypotheses

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/)
[![PennyLane](https://img.shields.io/badge/PennyLane-0.38+-teal.svg)](https://pennylane.ai)
[![GitHub issues](https://img.shields.io/badge/status-active-green.svg)]()
[![Quantum](https://img.shields.io/badge/topic-quantum-purple.svg)]()
[![QML](https://img.shields.io/badge/topic-QML-orange.svg)]()

<p align="center">
  <img src="assets/sticker.svg" alt="PennyLane Agent Hypotheses" width="200"/>
</p>

A collection of **5 ranked, testable hypotheses** for agent-driven hybrid quantum/ML experiments using the [PennyLane](https://pennylane.ai) demonstration suite.

## Goals

- Identify high-impact directions where hybrid quantum-classical models can demonstrate measurable advantage on small-scale benchmarks.
- Reduce simulator and hardware cost through FLOPs-aware architecture search, engineered dissipation, and post-variational strategies.
- Improve expressivity and trainability by leveraging neural architecture search, PDE-constrained losses, and trainable encoding schemes.

## Evaluation Metrics

All hypotheses are evaluated with consistent, reproducible metrics:

| Metric | Description |
|--------|-------------|
| **Accuracy** | Test-set classification accuracy (% or AUROC) |
| **Gradient variance** | Variance of cost-function gradients across random initialisations (barren plateau severity) |
| **Convergence speed** | Epochs or wall-clock time to reach threshold loss |
| **FLOPs / parameter count** | Computational resource footprint at iso-accuracy |
| **Pareto hypervolume** | Multi-objective quality of discovered architectures |
| **Fraction barren** | Percentage of random initialisations resulting in untrainable landscapes |

## Quickstart

```bash
# Clone and navigate
git clone https://github.com/NullLabTests/pennylane-agent-hypotheses.git
cd pennylane-agent-hypotheses

# Inspect hypotheses
cat hypotheses.json | python -m json.tool

# Each hypothesis references a baseline PennyLane demo from the
# pennylane/demos repository. For example, to run H1's baseline:
pip install pennylane
python demonstrations_v2/tutorial_variational_classifier/demo.py
```

## Hypotheses Overview

| # | Title | Area | Est. Cost |
|---|-------|------|-----------|
| H1 | Joint Classical–Quantum NAS for Pareto-Optimal HQNNs | Architecture Search | Medium |
| H2 | Engineered Dissipation vs. Local Cost for BP Mitigation | Trainability | Medium |
| H3 | Post-Variational Strategies on Non-Convex Landscapes | Expressivity/Cost | Low–Medium |
| H4 | PDE-Constrained Loss Functions Suppress Gradient Vanishing | Trainability | Medium |
| H5 | Data-Reuploading with Trainable Scaling on Small Benchmarks | Expressivity | Low–Medium |

See `hypotheses.json` for full details, references, and experiment plans.

## Repository Structure

```
├── hypotheses.json          # 5 ranked hypotheses (JSON array)
├── README.md                # This file
├── LICENSE                  # MIT License
└── assets/
    └── sticker.svg           # Project sticker / badge image
```

## Tags

`quantum` `pennylane` `qml` `agents` `experiments` `hybrid` `quantum-machine-learning` `variational-circuits`

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
