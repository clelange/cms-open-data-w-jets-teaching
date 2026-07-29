# CMS Open Data: from generator truth to missing momentum

This repository contains reusable Jupyter notebooks for introducing particle-physics event records with CMS Open Data. The material is aimed at high-school physics teachers and uses simulated W+jets events in NanoAOD format from [CERN Open Data record 69747](https://opendata.cern.ch/record/69747).

[![Open the main lesson in Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/clelange/cms-open-data-w-jets-teaching/blob/main/notebooks/w_to_munu_truth_met_69747.ipynb)

## Notebooks

- [`w_to_munu_truth_met_69747.ipynb`](notebooks/w_to_munu_truth_met_69747.ipynb) is the main lesson. It follows W → μν from the hard process and `GenPart` history to a reconstructed muon, missing transverse momentum, and transverse mass.
- [`truth_and_four_momentum_69747.ipynb`](notebooks/truth_and_four_momentum_69747.ipynb) is an advanced extension covering `LHEPart`, four-momentum conservation, generator-copy bookkeeping, and decay trees. [Open it in Google Colab](https://colab.research.google.com/github/clelange/cms-open-data-w-jets-teaching/blob/main/notebooks/truth_and_four_momentum_69747.ipynb).
- [`explore_69747.ipynb`](notebooks/explore_69747.ipynb) is a short technical introduction to opening NanoAOD with Uproot and manipulating jagged particle collections with Awkward Array.

The main and advanced notebooks are designed to run from top to bottom in Google Colab. Their setup cells install missing Python packages and download the approximately 133 MB input file when no local copy is available.

## Run locally

Use Python 3.11 or newer:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

Then open a notebook from `notebooks/`. A previously downloaded input file can be placed at:

```text
data/69747/00702195-E707-3743-8BBA-57EB9DEE1DBA.root
```

The advanced notebook also requires the Graphviz `dot` executable; its Colab setup installs this automatically.

The notebooks use [Uproot](https://uproot.readthedocs.io/) and [Awkward Array](https://awkward-array.org/) to read and analyze the ROOT file without requiring a full CMSSW installation.
