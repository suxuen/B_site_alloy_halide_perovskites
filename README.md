# Thermodynamic and Electronic Effects of B-site Alloying in Halide Perovskites

This repository contains the analysis code, data, and figure-generation notebooks for the manuscript:

> **Thermodynamic and Electronic Effects of B-site Alloying in Halide Perovskites**
> Suxuen Yew, John T. Barber, Christopher Sutton, and Charles B. Musgrave
> *Chemistry of Materials* (accepted; in press — DOI to be added upon publication)

## Abstract

Inorganic halide perovskites (IHPs) are promising optoelectronic materials, but the thermodynamic and electronic effects of B-site alloying across a broad chemical space remain poorly understood. Here, we perform a high-throughput study combining density functional theory (DFT) and machine-learned potentials (MLIPs) across more than 6,700 single (ABX3) and alloyed (AA'(BxB'1–x)2X6) IHP compositions to evaluate stabilities and band gaps. Our stability analysis shows that B-site alloying generally destabilizes perovskites relative to their constituent ABX3s, with 65.1% of alloys exhibiting positive mixing enthalpies. Despite this trend, alloy stability is highly dependent on their most stable constituent ABX3, revealing a practical design rule: stable ABX3s can improve stability of unstable ABX3s through alloying. Analysis of electronic properties reveals two distinct band gap behaviors from B-site alloying. Alloys composed of alkaline-earth metals (AEMs) and post-transition metals (PTMs) exhibit continuous band gap evolution driven by band edge energy alignment and spatial delocalization of s- and p-orbitals, enabling strong band edge coupling. In contrast, alloys involving transition metals (TMs) frequently exhibit discontinuous band gap changes due to the energetic misalignment and spatial localization of TM d-orbitals, which weakly couple to the s- and p-orbitals of AEMs and PTMs and d-orbitals of other TMs. Together, our findings provide design principles for improving the thermodynamic stability of halide perovskite alloys and predicting whether the band gap evolution will be continuous or discontinuous.

## Repository Status

🚧 **This repository is under active construction.** The thermodynamic stability analysis is populated and reproducible; the electronic structure analysis is still being added.

| Section | Notebook | Status |
|---|---|---|
| Thermodynamic stability (mixing/formation enthalpies, entropy, free energy) | [`1_thermodynamic.ipynb`](1_thermodynamic.ipynb) | Complete |
| Electronic structure (band gaps, orbital coupling/DOS analysis) | [`2_electronic.ipynb`](2_electronic.ipynb) | In progress |

## Repository Structure

```
.
├── 1_thermodynamic.ipynb      # Reproduces stability figures (dHmix, dHd, entropy/free energy)
├── 2_electronic.ipynb         # Electronic structure analysis (WIP)
├── data/
│   ├── DFT results/           # DFT-at-MLIP results and derived alloy/pure-phase dataframes
│   ├── DFT dos/                # Density-of-states data for electronic structure analysis (WIP)
│   ├── extraction scripts/     # Scripts used to extract/process raw DFT output (WIP)
│   └── oqmd data/              # OQMD elemental reference energies used for formation enthalpy calcs
└── manuscript_figures/         # Output figures matching manuscript figure numbers
```

## Reproducing the Figures

Each notebook reads data from `data/` (relative paths) and writes figures to `manuscript_figures/`. Notebook 1 currently reproduces:

- **Figure 2** — mixing enthalpy vs. decomposition enthalpy across all alloys
- **Figure 3** — alloy stability relative to the min/max stability of constituent ABX3 phases
- **Figure S6 / S7** — free energy of decomposition at T = 300 K / 500 K, incorporating configurational entropy

**Dependencies:** `pymatgen`, `ase`, `numpy`, `pandas`, `scipy`, `seaborn`, `matplotlib`. A pinned `environment.yml`/`requirements.txt` will be added once the environment is finalized.

## Citation

Citation details (BibTeX) will be added once the manuscript is formally published.
