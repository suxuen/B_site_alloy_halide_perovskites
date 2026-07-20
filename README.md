# Thermodynamic and Electronic Effects of B-site Alloying in Halide Perovskites

This repository contains the analysis code, data, and figure-generation notebooks for the manuscript:

> **Thermodynamic and Electronic Effects of B-site Alloying in Halide Perovskites**
> Suxuen Yew, John T. Barber, Christopher Sutton, and Charles B. Musgrave
> *Chemistry of Materials* (accepted — DOI to be added upon publication)

The high-throughput DFT/MLIP calculations underlying this dataset were run using the automated pipeline in [vasp_workflow](https://github.com/suxuen/vasp_workflow); this repository covers the downstream analysis and figure generation.

## Abstract

Inorganic halide perovskites (IHPs) are promising optoelectronic materials, but the thermodynamic and electronic effects of B-site alloying across a broad chemical space remain poorly understood. Here, we perform a high-throughput study combining density functional theory (DFT) and machine-learned potentials (MLIPs) across more than 6,700 single (ABX3) and alloyed (AA'(BxB'1–x)2X6) IHP compositions to evaluate stabilities and band gaps. Our stability analysis shows that B-site alloying generally destabilizes perovskites relative to their constituent ABX3s, with 65.1% of alloys exhibiting positive mixing enthalpies. Despite this trend, alloy stability is highly dependent on their most stable constituent ABX3, revealing a practical design rule: stable ABX3s can improve stability of unstable ABX3s through alloying. Analysis of electronic properties reveals two distinct band gap behaviors from B-site alloying. Alloys composed of alkaline-earth metals (AEMs) and post-transition metals (PTMs) exhibit continuous band gap evolution driven by band edge energy alignment and spatial delocalization of s- and p-orbitals, enabling strong band edge coupling. In contrast, alloys involving transition metals (TMs) frequently exhibit discontinuous band gap changes due to the energetic misalignment and spatial localization of TM d-orbitals, which weakly couple to the s- and p-orbitals of AEMs and PTMs and d-orbitals of other TMs. Together, our findings provide design principles for improving the thermodynamic stability of halide perovskite alloys and predicting whether the band gap evolution will be continuous or discontinuous.

## Repository Status

**This repository is under active construction.** The thermodynamic stability and electronic structure analysis is populated and reproducible; more commenting intended to improve clarity.

| Section | Notebook | Status |
|---|---|---|
| Thermodynamic stability (mixing/formation enthalpies, entropy, free energy) | [`1_thermodynamic.ipynb`](1_thermodynamic.ipynb) | Working notebook, needs commenting |
| Electronic structure (band gaps, orbital coupling/DOS analysis) | [`2_electronic.ipynb`](2_electronic.ipynb) | Working notebook, needs commenting |

## Repository Structure

```
.
├── 1_thermodynamic.ipynb       # Reproduces stability figures (dHmix, dHd, entropy/free energy)
├── 2_electronic.ipynb          # Electronic structure analysis (band gap bowing, pDOS)
├── data/
│   ├── DFT results/            # DFT-at-MLIP results and derived alloy/pure-phase dataframes
│   ├── DFT dos/                # Density-of-states data for electronic structure analysis
│   ├── extraction scripts/     # Scripts used to extract/process raw DFT output (**to be added**)
│   └── oqmd data/              # OQMD elemental reference energies used for formation enthalpy calcs
└── manuscript_figures/         # Output figures matching manuscript figure numbers
```

**Note on `dos_helper.py`:** the DOS/PDOS plotting utilities in this file were originally written by Nicholas Singstock, Ph.D., and are used here (with thanks) to help generate the density-of-states figures in `2_electronic.ipynb`.

## Reproducing the Figures

Each notebook reads data from `data/` (relative paths) and writes figures to `manuscript_figures/`. Notebook 1 currently reproduces:

- **Figure 2** — mixing enthalpy vs. decomposition enthalpy across all alloys
- **Figure 3** — alloy stability relative to the min/max stability of constituent ABX3 phases
- **Figure S6 / S7** — free energy of decomposition at T = 300 K / 500 K, incorporating configurational entropy
- **Figure 4** — (a) discontinuous vs (b) continuous band gap change vs composition
- **Figure 5 / 6** — Projected DOS of KRb(Mg_(1-x)Ni_(x))_2F_6 (discontinuous) and Cs_2(Sr_(1-x)Pb_(x))_2Br_6 (continuous)

**Dependencies:** `pymatgen`, `ase`, `numpy`, `pandas`, `scipy`, `seaborn`, `matplotlib`, `palettable` (if not specifying dos plot colours). A pinned `environment.yml`/`requirements.txt` will be added once the environment is finalized.

## Citation

Citation details will be added once the manuscript is formally published.

## Disclaimer

**Note on repository assembly:** The analysis code and scientific content in this repository were written by the authors (with dos_helper.py adapted from N. Singstock, credited above). Claude (Anthropic) was used to help organize and consolidate scattered PhD-era scripts into this repository's structure.
