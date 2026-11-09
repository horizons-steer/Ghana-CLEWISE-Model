# Ghana CLEWISE Model

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23984466.svg)](https://doi.org/10.5281/zenodo.23984466)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

**An integrated model of Ghana's Climate, Land, Energy, Water, Waste, and Industry for all Sectoral Emissions (CLEWISE).**

This repository holds the CLEWISE-Ghana model, the datasets behind it, model input and output files, and supporting documentation. It is the first integrated, all-sector model of its kind developed for Ghana, and it is built to be used as a development-planning tool rather than an emissions calculator.

Developed at the **STEER Centre, Loughborough University**.

---

## Overview

Developing countries face a twin challenge: expanding access to energy, water, food and mobility while aligning national development with global climate goals. These services are delivered through tightly coupled systems. Decisions about energy infrastructure reshape land use, water demand and emissions; choices in agriculture and water management feed back into energy needs and food security. Climate change intensifies these couplings, which makes sector-by-sector planning increasingly inadequate for long-term decisions.

For a government with limited fiscal space, the central question is not only how much a low-carbon transition reduces emissions, but whether it makes economic sense — how much must be invested, how much is saved in operating and fuel costs, and how large the wider development benefits are.

Under Article 4.19 of the Paris Agreement, Ghana has committed to aligning national development priorities with global climate objectives. This model was built to support that work. It compares three development pathways to 2056 and quantifies, for each, four decision-relevant quantities:

1. the capital investment required,
2. the operating-cost (including fuel) savings,
3. the avoided externality costs, or development co-benefits, and
4. the resulting greenhouse gas emissions.

On that basis it constructs a discounted net-economic-benefit account, asking whether the benefits of a net-zero pathway exceed its costs, and identifying where in the economy those net benefits arise.

---

## What CLEWISE adds

The established **CLEWs** framework (Climate, Land, Energy and Water systems) has been applied from global to urban scale across diverse contexts. Reviews of the field consistently identify two gaps that this work addresses.

**First**, most national CLEWs applications stop short of a full, monetised cost–benefit account that places the additional investment of a decarbonisation pathway alongside the operating-cost savings and avoided externalities it generates.

**Second**, coverage of industrial processes and the full set of IPCC emitting sectors is often partial, even though industry and waste are central to both emissions and development outcomes in fast-growing economies.

**CLEWISE** — *Climate, Land, Energy, Water, Waste, and Industry for all Sectoral Emissions* — extends CLEWs in two ways:

| Extension | What it means |
|---|---|
| **Industrial processes module** | Explicit representation of energy-intensive processes, notably cement and aluminium, alongside energy, agriculture and land use, buildings, transport, water and waste |
| **Complete IPCC sectoral emissions** | Accounts for emissions across energy, industrial processes and product use (IPPU), agriculture, forestry and other land use (AFOLU), and waste — so the framework that tracks resource flows also produces an internally consistent GHG inventory |

---

## Model architecture

The model is built in **OSeMOSYS** (Open Source Energy Modelling System) using the **Model User Interface (MUI) v5.6** — a cost-free, bottom-up, linear cost-optimisation environment widely applied to national energy and climate planning.

OSeMOSYS identifies the least-cost combination of technologies and investments that meets exogenously defined demands over a given horizon, subject to technical, resource and policy constraints. Each technology is represented through input/output activity ratios and techno-economic parameters — capital, fixed and variable costs, capacity factors, and operational lifetimes.

### Specification

| Parameter | Value |
|---|---|
| **Modelling framework** | OSeMOSYS, via Model User Interface (MUI) v5.6 |
| **Horizon** | 2020–2056 (2056 precedes Ghana's centenary of independence) |
| **Temporal resolution** | 8 time slices — 2 seasons × 4 daily periods |
| **Seasons** | Dry (November–March), wet (April–October) |
| **Daily periods** | Peak, shoulder peak, intermediate, base |
| **Load profile source** | Energy Commission of Ghana, 2023 national load data |
| **Discount rate** | 5% real |

### Sectors represented

- **Power** — hydro, thermal, solar PV (on- and off-grid), wind, nuclear, imports and exports
- **Buildings** — residential and commercial; cooking, heating, appliances
- **Industry** — including explicit cement and aluminium process representation
- **Transport** — cars, buses, motorcycles, heavy and medium freight, rail
- **Agriculture and land use** — crops under four input regimes, livestock, forestry, reforestation
- **Water** — public supply, agricultural demand, thermal cooling, hydropower
- **Waste** — solid and liquid waste generation, treatment and methane emissions

### Cross-sectoral linkages

The model represents resource flows between systems explicitly, which is the point of an integrated approach — these interactions are invisible to single-sector analysis:

- Water for thermal-plant cooling and for hydropower
- Energy for water pumping, treatment and irrigation
- Energy and land for agriculture
- Land footprint for energy infrastructure
- Energy for fertiliser production and field preparation
- Crop water demand under rainfed and irrigated, high- and low-input regimes

---

## The dataset

### Published and archived on Zenodo

The underlying dataset is published open access with a permanent DOI, so it can be cited and retrieved independently of this repository.

| | |
|---|---|
| **Title** | A Techno-economic Dataset for Climate, Land, Energy, Water, Waste, and Industry for all Sectoral Emissions (CLEWISE) modelling in Ghana |
| **DOI** | [10.5281/zenodo.23984466](https://doi.org/10.5281/zenodo.23984466) |
| **Version** | v1, published 5 November 2026 |
| **Licence** | Creative Commons Attribution 4.0 International (CC BY 4.0) |
| **Community** | [Horizons STEER](https://zenodo.org/communities/horizons-lu/records) |

The record contains the full techno-economic workbook (`Ghana_CLEWISE Techno-economic data updated.xlsx`) and the accompanying data descriptor. The dataset informed the design of Ghana's Long-Term Low Emission Development Strategy.

**Use the DOI rather than this repository's URL when citing the data.** A DOI is permanent and resolves even if the repository is renamed, moved or archived, which is what journals expect in a data availability statement.

### About the data

The model is underpinned by an open, techno-economic dataset compiled specifically for Ghana. It is organised as an Excel workbook for transparency and ease of use, and adheres to the **U4RIA principles** — Ubuntu, Retrievability, Repeatability, Reconstructability, Interoperability and Auditability.

Although designed for OSeMOSYS, its MUI, and the Data-to-Deal (D2D) framework, the dataset is an independent, openly accessible resource that can be adapted for other modelling frameworks.

### Coverage

| Domain | Contents |
|---|---|
| **Energy supply** | Installed and residual capacity by plant, historical and projected generation, electricity import/export, capacity factors, transmission and distribution losses |
| **Energy demand** | Fuel consumption by end-use sector 2020–2023 and projections to 2056; transport vehicle demand by mode; cement and aluminium production |
| **Resources** | Fossil fuel reserves and renewable energy potential |
| **Land** | Historical and projected land cover, crop area harvested, production, demand, yields, residual capacity, livestock numbers and methane emission factors |
| **Water** | Availability, usage patterns, precipitation, groundwater and surface water, evapotranspiration, crop water demand, water input activity ratios for energy and land technologies |
| **Waste** | Solid and liquid waste volumes and associated methane emissions |
| **Techno-economic** | Capital, fixed and variable costs for power, end-use, transport, crop and land-use technologies; operational lifetimes; global warming potentials and emission factors |

### Value of the dataset

- Enables continuation of modelling activities and in-country capacity building within Ghana
- Supports development of a long-term transition framework and exploration of land–food–water–energy interconnections
- Allows development and comparison of alternative scenario frameworks
- Addresses documented data gaps in the Ghanaian and wider Sub-Saharan African literature
- Can inform national investment needs in key technologies and infrastructure, following the Data-to-Deal approach
- Helps development partners and private investors identify viable, high-impact opportunities aligned with Ghana's long-term sustainability goals

---

## Getting started

## Data sources and co-creation

The dataset was compiled through a collaborative process involving national institutions, local consultants and sectoral stakeholders:

- **Energy Commission of Ghana**
- **Ministry of Environment, Science, Technology and Innovation (MESTI)**
- **Environmental Protection Agency (EPA)**
- **National Development Planning Commission (NDPC)**
- **Ministry of Energy**
- **Ministry of Food and Agriculture (MoFA)**
- **Driver and Vehicle Licensing Authority (DVLA)**

International and secondary sources include the IEA, IRENA, FAO and FAOSTAT, the Global Agro-Ecological Zones (GAEZ) database, OECD, WHO, IMF, the World Bank and the World Resources Institute, alongside peer-reviewed literature and national technical reports.

All collected data were processed to align with the modelling framework's requirements. Sources were converted into common units — GW for capacity, PJ for energy, BCM for water — with reporting periods harmonised, inconsistencies between sources resolved, and gaps addressed through interpolation or validated assumptions. Costs were converted to 2022 US dollars using a WRI GDP deflator.

---

## Limitations

**Data availability and quality** is the main constraint. Technology costs, fuel-use shares, sectoral demand patterns and operational characteristics sometimes rely on default values, international databases or expert judgement where consistent, up-to-date national data are unavailable. Some parameters are derived from West African regional trends rather than Ghana-specific observations.

**Model assumptions.** OSeMOSYS assumes perfect foresight and least-cost behaviour in competitive markets, which may understate real-world frictions, financing constraints and behavioural inertia.

**Projections.** Future demand projections rest on trend and growth-rate assumptions; more sophisticated approaches would improve accuracy.

**Priorities for refinement.** Better country-specific data is most needed on end-use energy consumption by activity, vehicle fleet composition and usage, livestock emission factors, and solid-waste generation and treatment.

**Scope for extension.** Future work could integrate green hydrogen production and use, fertiliser production and use in agriculture, and additional externalities including ecosystem services, biodiversity, nutrition, active mobility, employment creation and socio-economic resilience.

---
## Citation

If you use this model or its underlying dataset in your work, please cite them as follows.

### Dataset

The dataset has a permanent DOI and should be cited directly:

> Akpahou, R., Alfstad, T., & Quirós-Tortós, J. (2026). *A Techno-economic Dataset for Climate, Land, Energy, Water, Waste, and Industry for all Sectoral Emissions (CLEWISE) modelling in Ghana* (v1) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.23984466

### Repository

> Akpahou, R., Alfstad, T., & Quirós-Tortós, J. (2026). *Ghana CLEWISE Model: an integrated model of Ghana's Climate, Land, Energy, Water, Waste, and Industry for all Sectoral Emissions (CLEWISE)* [Software and data]. STEER Centre, Loughborough University. https://github.com/horizons-steer/Ghana-CLEWISE-Model

### Publications

> Akpahou, R., Alfstad, T., & Quirós-Tortós, J. *The economic case for net zero in Ghana: an integrated CLEWISE assessment of investment needs, operating savings and development benefits.*

> Akpahou, R., Alfstad, T., & Quirós-Tortós, J. *Integrated System Analysis in Developing Countries: A Techno-economic Dataset for Climate, Land, Energy, and Water system (CLEWs) modelling in Ghana.* Data in Brief.

A `CITATION.cff` file is included in the repository root, so GitHub displays a **Cite this repository** button on the repository page with ready-formatted APA and BibTeX entries.

### BibTeX

```bibtex
@dataset{akpahou_clewise_ghana_data_2026,
  author    = {Akpahou, Romain and Alfstad, Thomas and Quir{\'o}s-Tort{\'o}s, Jairo},
  title     = {A Techno-economic Dataset for Climate, Land, Energy, Water,
               Waste, and Industry for all Sectoral Emissions ({CLEWISE})
               modelling in Ghana},
  year      = {2026},
  publisher = {Zenodo},
  version   = {v1},
  doi       = {10.5281/zenodo.23984466},
  url       = {https://doi.org/10.5281/zenodo.23984466}
}

@software{akpahou_ghana_clewise_2026,
  author    = {Akpahou, Romain and Alfstad, Thomas and Quir{\'o}s-Tort{\'o}s, Jairo},
  title     = {Ghana {CLEWISE} Model: an integrated model of Ghana's Climate,
               Land, Energy, Water, Waste, and Industry for all Sectoral
               Emissions ({CLEWISE})},
  year      = {2026},
  publisher = {STEER Centre, Loughborough University},
  url       = {https://github.com/horizons-steer}
}
```

---

*The CLEWISE framework and its net-economic-benefit accounting are transferable. They can be applied wherever integrated, development-oriented decarbonisation planning is needed, providing a consistent way to compare the costs, savings and co-benefits of alternative pathways across sectors and countries.*
