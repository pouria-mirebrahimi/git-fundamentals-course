# Project Structure Overview

This document explains the folder structure of the project and the purpose of each directory and file. The layout follows best practices for organizing a Machine Learning (ML) project — supporting reproducibility, scalability, and clarity.

```
.
├── config.yml
├── data
│   ├── external
│   ├── processed
│   └── raw
├── doc
├── experiments
├── LICENSE
├── models
├── notebooks
├── README.md
├── requirements.txt
├── scripts
├── setup.py
├── src
│   ├── data
│   ├── features
│   ├── models
│   └── visualization
├── tests
└── utils
```

---

## Root Files

* **`config.yml`** — Central configuration file containing parameters, paths, and hyperparameters used throughout the project. Makes experiments reproducible and flexible.
* **`requirements.txt`** — Lists all Python dependencies required to run the project.
* **`setup.py`** — Setup script for packaging and installation; allows `src` to be installed as a module (e.g., `pip install -e .`).
* **`LICENSE`** — License file specifying the usage rights of the project.
* **`README.md`** — Primary documentation file providing an overview of the project, installation instructions, and usage details.

---

## Data Folder

* **`data/raw/`** — Original, immutable data as received from the source. Should never be modified directly.
* **`data/processed/`** — Cleaned and preprocessed data ready for model training or analysis.
* **`data/external/`** — Datasets from external sources or third-party APIs that supplement the main data.

---

## Documentation

* **`doc/`** — Contains project documentation, such as research notes, architecture diagrams, reports, or API documentation.

---

## Experiments

* **`experiments/`** — Stores experiment results, logs, trained models’ metrics, or configuration snapshots. Helps track progress and compare different experiment runs.

---

## Models

* **`models/`** — Saved trained models, checkpoints, and serialized files (e.g., `.pkl`, `.pt`, `.h5`). Ensures reproducibility and version tracking.

---

## Notebooks

* **`notebooks/`** — Jupyter notebooks used for exploration, data analysis, visualization, and prototyping before integrating code into the main pipeline.

---

## Scripts

* **`scripts/`** — Utility scripts or command-line tools for automating tasks such as data downloading, model evaluation, or deployment.

---

## Source Code (`src/`)

The core implementation of the project is organized in modular subpackages:

* **`src/data/`** — Scripts for loading, cleaning, and transforming data.
* **`src/features/`** — Feature engineering and extraction logic.
* **`src/models/`** — Model definitions, training, validation, and inference pipelines.
* **`src/visualization/`** — Scripts for generating plots, dashboards, or visual reports.

---

## Tests

* **`tests/`** — Unit and integration tests to ensure code reliability, correctness, and reproducibility across modules.

---

## Utils

* **`utils/`** — General-purpose helper functions (e.g., logging, configuration loading, metrics calculation) that are reused across modules.