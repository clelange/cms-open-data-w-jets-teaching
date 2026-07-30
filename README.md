# CMS Open Data: from generator truth to missing momentum

This repository contains reusable Jupyter notebooks for introducing particle-physics event records with CMS Open Data. The material is aimed at high-school physics teachers and uses simulated W+jets events in NanoAOD format from [CERN Open Data record 69747](https://opendata.cern.ch/record/69747).

[![Open the main lesson in Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/clelange/cms-open-data-w-jets-teaching/blob/main/notebooks/w_to_munu_truth_met_69747.ipynb)

## Notebooks

- [`w_to_munu_truth_met_69747.ipynb`](notebooks/w_to_munu_truth_met_69747.ipynb) is the main lesson. It follows W → μν from the hard process and `GenPart` history to a reconstructed muon, missing transverse momentum, and transverse mass.
- [`truth_and_four_momentum_69747.ipynb`](notebooks/truth_and_four_momentum_69747.ipynb) is an advanced extension covering `LHEPart`, four-momentum conservation, generator-copy bookkeeping, and decay trees. [Open it in Google Colab](https://colab.research.google.com/github/clelange/cms-open-data-w-jets-teaching/blob/main/notebooks/truth_and_four_momentum_69747.ipynb).
- [`explore_69747.ipynb`](notebooks/explore_69747.ipynb) is an optional technical warm-up for opening NanoAOD with Uproot and manipulating jagged particle collections with Awkward Array.

For a conceptual route, start directly with the main lesson and then continue to the advanced extension. Use the technical warm-up first only if you want additional practice with the Python data tools.

The notebooks are designed to run from top to bottom in Google Colab. Their setup cells install missing Python packages and use XRootD to stream the requested data directly from CERN Open Data, so no 133 MB file download is required.

## Run locally

Use Python 3.11 or newer:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

Then open a notebook from `notebooks/`. The notebooks require a network connection while running because they read the ROOT file directly from `eospublic.cern.ch` through XRootD.

The advanced notebook also requires the Graphviz `dot` executable; its Colab setup installs this automatically.

The notebooks use [Uproot](https://uproot.readthedocs.io/), [Awkward Array](https://awkward-array.org/), and the Python XRootD interface to read and analyze the remote ROOT file without requiring a full CMSSW installation.
