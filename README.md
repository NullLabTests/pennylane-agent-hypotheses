<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/sticker.svg">
    <img src="assets/sticker.svg" alt="PennyLane Agent Hypotheses" width="160"/>
  </picture>
</p>

<h1 align="center">🧪 PennyLane Agent Hypotheses</h1>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square&logo=opensourceinitiative" alt="License"></a>
  <a href="https://www.python.org/"><img src="https://img.shields.io/badge/Python-3.10+-blue.svg?style=flat-square&logo=python" alt="Python"></a>
  <a href="https://pennylane.ai"><img src="https://img.shields.io/badge/PennyLane-0.38+-teal.svg?style=flat-square&logo=quantum" alt="PennyLane"></a>
  <a href="https://github.com/NullLabTests/pennylane-demos"><img src="https://img.shields.io/badge/Demos-fork-7C3AED?style=flat-square&logo=github" alt="Demos"></a>
  <a href="https://github.com/NullLabTests/pennylane-agent-experiments"><img src="https://img.shields.io/badge/Experiments-runnable-10B981?style=flat-square" alt="Experiments"></a>
  <a href="#"><img src="https://img.shields.io/badge/Status-Active-success?style=flat-square&logo=activity" alt="Status"></a>
</p>

<p align="center">
  <b>5 ranked, testable hypotheses</b> for agent-driven hybrid quantum/ML experiments<br/>
  using the <a href="https://pennylane.ai">PennyLane</a> demonstration suite.
</p>

<br/>

---

## 🎯 Overview

This repository defines the **research agenda** for a suite of agent-generated experiments exploring practical advantages in hybrid quantum-classical machine learning. Each hypothesis is grounded in recent theoretical results, references concrete PennyLane baselines, and specifies falsifiable metrics with estimated computational cost.

<br/>

### 🔗 Ecosystem

```mermaid
graph TB
    subgraph Planning["📋 Planning Layer"]
        H[("🧪<br/>agent-hypotheses<br/><i>This Repo</i>")]
    end
    subgraph Implementation["⚙️ Implementation Layer"]
        D[("🐍<br/>pennylane-demos<br/><i>Fork with Python scripts</i>")]
    end
    subgraph Execution["▶️ Execution Layer"]
        E[("📓<br/>pennylane-agent-experiments<br/><i>Notebooks + CI</i>")]
    end
    H -->|"defines & references"| D
    D -->|"packaged as"| E
    E -->|"validates"| H
    D -.->|"upstream"| U[("🔬<br/>PennyLaneAI/demos")]
    style H fill:#1a1a2e,stroke:#00d4aa,stroke-width:3,color:#fff
    style D fill:#1a1a2e,stroke:#7C3AED,stroke-width:3,color:#fff
    style E fill:#1a1a2e,stroke:#10B981,stroke-width:3,color:#fff
    style U fill:#333,stroke:#666,stroke-width:1,color:#999
```

<br/>

### 📦 Sister Repositories

| Badge | Repository | Role |
|-------|-----------|------|
| <img src="https://img.shields.io/badge/Code-Python%20scripts-7C3AED?style=flat-square"> | [pennylane-demos](https://github.com/NullLabTests/pennylane-demos) | Fork of PennyLaneAI/demos with Python implementations of each hypothesis |
| <img src="https://img.shields.io/badge/Run-Jupyter%20notebooks-10B981?style=flat-square"> | [pennylane-agent-experiments](https://github.com/NullLabTests/pennylane-agent-experiments) | Runnable notebooks, YAML configs, CI smoke tests |

<br/>

---

## 📋 Hypotheses

<p align="center">

| # | Title | Area | Est. Cost | Status |
|:-:|-------|:----:|:---------:|:------:|
| **H1** | Joint Classical–Quantum NAS for Pareto-Optimal HQNNs | <img src="https://img.shields.io/badge/Architecture%20Search-8B5CF6?style=flat-square"> | <img src="https://img.shields.io/badge/Medium-F59E0B?style=flat-square"> | <img src="https://img.shields.io/badge/Definition%20Complete-success?style=flat-square"> |
| **H2** | Engineered Dissipation vs. Local Cost for BP Mitigation | <img src="https://img.shields.io/badge/Trainability-3B82F6?style=flat-square"> | <img src="https://img.shields.io/badge/Medium-F59E0B?style=flat-square"> | <img src="https://img.shields.io/badge/Definition%20Complete-success?style=flat-square"> |
| **H3** | Post-Variational Strategies on Non-Convex Landscapes | <img src="https://img.shields.io/badge/Expressivity-EF4444?style=flat-square"> | <img src="https://img.shields.io/badge/Low--Medium-84CC16?style=flat-square"> | <img src="https://img.shields.io/badge/Definition%20Complete-success?style=flat-square"> |
| **H4** | PDE-Constrained Loss Functions Suppress Gradient Vanishing | <img src="https://img.shields.io/badge/Trainability-3B82F6?style=flat-square"> | <img src="https://img.shields.io/badge/Medium-F59E0B?style=flat-square"> | <img src="https://img.shields.io/badge/Definition%20Complete-success?style=flat-square"> |
| **H5** | Data-Reuploading with Trainable Scaling on Small Benchmarks | <img src="https://img.shields.io/badge/Expressivity-EF4444?style=flat-square"> | <img src="https://img.shields.io/badge/Low--Medium-84CC16?style=flat-square"> | <img src="https://img.shields.io/badge/Definition%20Complete-success?style=flat-square"> |

</p>

Each hypothesis in [`hypotheses.json`](hypotheses.json) includes:

| Section | Description |
|---------|-------------|
| **Description & rationale** | What is being tested and why it matters |
| **Novelty rationale** | How it differs from prior work |
| **Expected metrics** | Quantitative success criteria for falsifiability |
| **Baseline notebook** | Corresponding PennyLane demo path |
| **References** | Supporting papers with arXiv links |

<br/>

---

## 📊 Evaluation Metrics

```mermaid
mindmap
  root((Metrics))
    Accuracy
      Test-set classification %
      AUROC score
    Gradient Variance
      Cost-function gradients
      Random initialisations
    Convergence Speed
      Epochs to threshold
      Wall-clock time
    Resource Footprint
      FLOPs per forward pass
      Parameter count
    Pareto Hypervolume
      Multi-objective quality
      Accuracy vs cost
    Fraction Barren
      Untrainable landscapes
      Initialisation sensitivity
```

All experiments share these six metrics for consistent cross-hypothesis comparison.

<br/>

---

## 🚀 Quickstart

```bash
# Inspect the hypothesis definitions
cat hypotheses.json | python -m json.tool

# Run a baseline demo (e.g., H1 — Variational Classifier)
pip install pennylane
python -c "import pennylane as qml; print('PennyLane', qml.__version__)"
```

For executable experiments with notebooks and configs, visit the <a href="https://github.com/NullLabTests/pennylane-agent-experiments"><img src="https://img.shields.io/badge/Experiments-runnable-10B981?style=flat-square"></a> repo.

<br/>

---

## 📁 Repository Structure

```
📦 pennylane-agent-hypotheses
├── 📄 hypotheses.json       # 5 ranked hypotheses (JSON, machine-readable)
├── 📄 README.md             # This file
├── 📄 LICENSE               # MIT License
└── 📁 assets/
    └── 🖼️ sticker.svg       # Project visual identity
```

<br/>

---

## 📄 License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.
