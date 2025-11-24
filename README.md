# SBI‑Workshop‑Legend2025

This repository contains materials for a hands‑on workshop on **simulation‑based inference (SBI)** in population genetics.  The workshop is organised around a series of Jupyter notebooks that gradually introduce SBI methods, demonstrate toy examples, and apply these techniques to coalescent simulations using the [`msprime`](https://tskit.dev/msprime/docs/stable) library.

## Repository structure

```
sbi_workshop_Legend2025/
├── LICENSE                
├── README.md              # This overview
├── requirements.yaml      # Conda environment specification
└── notebooks/             # Jupyter notebooks for the workshop
      ├── 1_introduction_to_sbi.ipynb
      ├── 2_data_simulation_msprime.ipynb
      ├── 3_SBI_in_popgen.ipynb
      ├── 4_complex_scenario.ipynb
      └── 5_snakemake_workflow.ipynb

```

## Getting started

We recommend using **Visual Studio Code** or JupyterLab for exploring the notebooks.  To set up a working environment:

0. **Clone this github repository**:
   ```bash
   git clone git@github.com:ningyuxin1999/SBI-WORKSHOP-LEGEND2025.git
   ```
1. **Install Conda**: If you do not already have a conda distribution (e.g., Miniconda), install it from <https://docs.conda.io/en/latest/miniconda.html>.
2. **Create an environment**: Use the provided `requirements.yaml` to create a reproducible environment:

   ```bash
   conda env create -f requirements.yaml
   conda activate sbi-workshop
   ```

3. **install sbi**: Install the sbi package using pip within your conda environment:

   ```bash
   pip install sbi
   ```
   If you are running out of local disk space use
   ```bash
   TMPDIR=/path/to/folder/with/spacer pip install sbi
   ```
   instead.

4. **Launch notebooks**: Open the notebooks folder in VS Code or run

   ```bash
   jupyter notebook notebooks/
   ```

The `requirements.yaml` file lists the core dependencies (`msprime`, `tskit`, `torch`, `sbi`, `matplotlib`, etc.).  Feel free to install additional packages manually.

## Notebook overview

1. **Introduction to SBI** – outlines the motivation behind SBI, explains the main algorithms implemented in the [`sbi` toolkit](https://sbi-dev.github.io/sbi), and includes a warm‑up example inferring the mean of a normal distribution.
2. **Data simulation (msprime)** – demonstrates how to simulate ancestry and mutations with `msprime` and compute basic summary statistics like the site frequency spectrum (SFS).  It highlights that `msprime` version 1.0 efficiently implements ancestry and mutation simulation using the succinct tree sequence data structure.
3. **SBI in population genetics** – uses `msprime` to simulate DNA sequences under a constant population size and infers the effective population size from the number of segregating sites.
4. **Complex scenario** – simulates a two‑epoch population size change and examines how demographic events affect the SFS.
5. **Snakemake workflow** – describes how the [popgensbi_snakemake](https://github.com/kr-colab/popgensbi_snakemake) pipeline can be integrated into the workshop. The workflow runs training and prediction tasks via Snakemake and uses configuration files to specify simulation and inference settings.

## Contributing

...
