# 🔊 Acoustic Absorption Predictor

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/Version-1.0-green.svg)](https://github.com/yourusername/acoustic-absorption-predictor)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.xxxxxxx.svg)](https://doi.org/10.5281/zenodo.18675581)
[![Live Tool](https://img.shields.io/badge/Live%20Tool-alphaporous.com-orange.svg)](https://alphaporous.com)

> A free, open-access, browser-based tool for predicting sound absorption coefficients of porous materials using seven established acoustic models — no installation, no sign-up required.

**🌐 Live at:** [alphaporous.com](https://alphaporous.com)

---

## Overview

The **Acoustic Absorption Predictor** allows researchers, engineers, and students to predict the frequency-dependent sound absorption coefficient α(f) of porous materials directly in the browser. It implements seven acoustic models ranging from simple empirical fits to full poroelastic theory, making it suitable for:

- Material design and optimisation
- Experimental validation against impedance tube data
- Parametric studies (thickness, flow resistivity, porosity)
- Multilayer composite absorber simulation
- Academic coursework and teaching

---

## Features

- **7 Acoustic Models** — Delany-Bazley, Miki, JCA, JCAL (Lafarge), Biot, Zwikker-Kosten, TMM
- **Interactive Chart** — frequency-resolved α(f) with hover tooltip
- **NRC Calculation** — automatic Noise Reduction Coefficient at 250, 500, 1000, 2000 Hz
- **Multi-curve Overlay** — compare models and parameters side by side
- **TMM 2-Layer Simulation** — chain two material layers for composite absorbers
- **CSV Export** — download full frequency data for Excel / Python / MATLAB
- **No Dependencies** — single HTML file, runs entirely client-side
- **No Data Collection** — nothing is sent to any server

---

## Models Implemented

| Model | Category | Required Parameters |
|-------|----------|-------------------|
| Delany-Bazley | Empirical | σ, d |
| Miki | Empirical | σ, d |
| JCA | Semi-Empirical | σ, φ, α∞, Λ, Λ', d |
| JCAL (Lafarge) | Semi-Empirical | σ, φ, α∞, Λ, Λ', k'₀, d |
| Biot | Semi-Empirical | σ, φ, α∞, Λ, Λ', E, ν, η_s, d |
| Zwikker-Kosten | Phenomenological | σ, φ, α∞, r, d |
| TMM (2-layer) | Phenomenological | Two layers, any model |

---

## Quick Start

**Option 1 — Use online:**
Visit [alphaporous.com](https://alphaporous.com) — nothing to install.

**Option 2 — Run locally:**
```bash
git clone https://github.com/yourusername/acoustic-absorption-predictor.git
cd acoustic-absorption-predictor
# Open alphaporous.html in any modern browser
open alphaporous.html
```

That's it — no build step, no server, no dependencies.

---

## Usage

1. **Select a model** from the left sidebar
2. **Enter material parameters** — type freely or use ↑↓ arrow keys to adjust values
3. **Click "+ Add to Chart"** to plot the absorption curve
4. **Add more curves** to compare models or parameter sets
5. **Switch tabs** to view the NRC Table or Data Table
6. **Export CSV** for further analysis

For detailed instructions see the [User Guide](docs/AAP_UserGuide_v1.pdf).

---

## Parameter Reference

| Parameter | Symbol | Unit | Typical Range |
|-----------|--------|------|---------------|
| Flow Resistivity | σ | Pa·s/m² | 5,000 – 50,000 |
| Thickness | d | mm | 10 – 200 |
| Porosity | φ | — | 0.1 – 0.99 |
| Tortuosity | α∞ | — | 1.0 – 3.0 |
| Viscous Char. Length | Λ | μm | 20 – 300 |
| Thermal Char. Length | Λ' | μm | 40 – 600 |
| Static Thermal Perm. | k'₀ | ×10⁻¹¹ m² | 1 – 100 |
| Pore Radius | r | μm | 10 – 200 |
| Frame Modulus | E | kPa | 10 – 10,000 |
| Poisson's Ratio | ν | — | 0.1 – 0.45 |
| Frame Loss Factor | η_s | — | 0.01 – 0.2 |

---

## Air Properties Used

All computations use standard air at 20°C:

| Property | Value |
|----------|-------|
| Density ρ₀ | 1.213 kg/m³ |
| Speed of sound c₀ | 343 m/s |
| Characteristic impedance Z₀ | 415.86 Pa·s/m |
| Dynamic viscosity η | 1.84 × 10⁻⁵ Pa·s |
| Ambient pressure P₀ | 101,325 Pa |
| Heat capacity ratio γ | 1.4 |
| Prandtl number Pr | 0.711 |

---

## Project Structure

```
acoustic-absorption-predictor/
│
├── alphaporous.html        # Main tool — single self-contained file
├── README.md               # This file
├── LICENSE                 # MIT License
└── docs/
    └── AAP_UserGuide_v1.pdf   # Full user guide with references and glossary
```

---

## Theoretical Background

The tool implements the following acoustic models. Key references:

- **Delany & Bazley (1970)** — *Applied Acoustics, 3*(2), 105–116
- **Miki (1990)** — *J. Acoust. Soc. Japan (E), 11*(1), 19–24
- **Johnson, Koplik & Dashen (1987)** — *J. Fluid Mechanics, 176*, 379–402
- **Champoux & Allard (1991)** — *J. Applied Physics, 70*(4), 1975–1979
- **Lafarge et al. (1997)** — *J. Acoust. Soc. America, 102*(4), 1995–2006
- **Biot (1956)** — *J. Acoust. Soc. America, 28*(2), 168–178
- **Zwikker & Kosten (1949)** — *Sound Absorbing Materials*, Elsevier
- **Allard & Atalla (2009)** — *Propagation of Sound in Porous Media* (2nd ed.), Wiley

---

## Citing This Work

If you use this tool in your research, please cite:

**APA:**
> Olajide, J. L. (2026). *Acoustic Absorption Predictor: A browser-based tool for porous material acoustic modelling* [Web application]. University of South Africa (UNISA). https://alphaporous.com

**BibTeX:**
```bibtex
@misc{olajide2026acoustictool,
  author      = {Olajide, Jimmy Lolu},
  title       = {Acoustic Absorption Predictor: A Browser-Based Tool
                 for Porous Material Acoustic Modelling},
  year        = {2026},
  institution = {University of South Africa (UNISA)},
  note        = {Open-access web tool. Available at: https://alphaporous.com},
  doi         = {10.5281/zenodo.18675581}
}
```

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

You are free to use, modify, and distribute this tool for academic and research purposes. Attribution is appreciated.

---

## Author

**Jimmy Lolu Olajide**
Computational Materials Scientist · Postgraduate Researcher
Department of Mechanical, Bioresources and Biomedical Engineering
University of South Africa (UNISA) · Florida Campus

[![ResearchGate](https://img.shields.io/badge/ResearchGate-Profile-00CCBB.svg)](https://www.researchgate.net/profile/Jimmy-Olajide)
[![Google Scholar](https://img.shields.io/badge/Google%20Scholar-Profile-4285F4.svg)](https://scholar.google.com/citations?user=HulJMpkAAAAJ)

---

## Contributing

Contributions, bug reports, and feature suggestions are welcome. Please open an issue or submit a pull request.

Potential future additions:
- Oblique incidence models
- Random incidence (Paris formula) integration
- Additional empirical models (Mechel, Kirby-Cummings)
- Material database with preset parameters
- Multilayer TMM beyond 2 layers

---

*Built for open academic use · alphaporous.com*
