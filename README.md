# Mach-Zehnder-Interferometer-in-Meep
Open-source FDTD simulation of a silicon-photonic Mach–Zehnder interferometer (MZI), written in Python with [Meep](https://meep.readthedocs.io) and runnable in Google Colab.
# Mach–Zehnder Interferometer in Meep

Open-source FDTD simulation of a silicon-photonic Mach–Zehnder interferometer (MZI), written in Python with [Meep](https://meep.readthedocs.io) and runnable in Google Colab.

## Features
- Parametric MZI layout: two directional couplers and two arms with path difference ΔL
- Automatic coupler-length sweep to find the 50:50 point
- Mode-source excitation and eigenmode monitors over 1.5–1.6 µm
- S-parameters for inputs P0 and P1 (outputs P2, P3)
- FDTD vs. circuit-model comparison
- Study of ΔL vs. free spectral range, with an interactive slider
- Corner cases: Si thickness ±2 nm, width ±5 nm
- Export to `.npz` and `.gds`

## Parameters
| Parameter | Value |
|---|---|
| Core / cladding | Si (n = 3.476) / SiO2 (n = 1.444) |
| Silicon thickness | 220 nm |
| Strip width | 450 nm |
| Coupler gap | 100 nm |
| Port half-separation | 1.5 µm |
| Bend radius | 3 µm |
| Path difference | 5 µm (simulation), 10 µm (GDS) |
| Band | 1.5–1.6 µm, TE-like |

## Usage
1. Open the notebook in Google Colab.
2. Run the install cells (condacolab + `pymeep`; the runtime restarts once).
3. Run the remaining cells in order.

## Results 
- **Directional coupler:** 50:50 near 1.546 µm; through/cross vary from about -2.4 to -3.9 dB across 1.5–1.6 µm.
- **MZI (ΔL = 5 µm):** P2 has a null near 1.52 µm and exceeds 90% toward 1.6 µm. P0 and P1 inputs give mirrored responses.
- **FDTD vs. circuit model:** same shape; FDTD is shifted about 9 nm to longer wavelengths and has slightly lower peaks (about 0.9 vs. 0.98).
- **Fabrication corners:** thickness ±2 nm and width ±5 nm shift the spectrum by about ±10 nm.

## Requirements
Python 3, `pymeep`, `numpy`, `matplotlib`, `ipywidgets`, `gdstk`.

