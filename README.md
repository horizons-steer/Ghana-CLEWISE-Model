# Ghana CLEWISE Model

**An integrated model of Ghana's climate, land, energy, water, waste and industry systems, accounting for all IPCC sectoral emissions.**

This repository holds the CLEWISE-Ghana model, the datasets behind it, model input and output files, and supporting documentation. It is the first integrated, all-sector model of its kind developed for Ghana, and it is built to be used as a development-planning tool rather than an emissions calculator.

Developed at the **STEER Centre, Loughborough University**, in co-creation with Ghanaian national institutions.

---

## Contents

- [Overview](#overview)
- [What CLEWISE adds](#what-clewise-adds)
- [Model architecture](#model-architecture)
- [Scenarios](#scenarios)
- [The cost–benefit framework](#the-costbenefit-framework)
- [Headline results](#headline-results)
- [The dataset](#the-dataset)
- [Repository structure](#repository-structure)
- [Getting started](#getting-started)
- [Data sources and co-creation](#data-sources-and-co-creation)
- [Limitations](#limitations)
- [Citation](#citation)
- [Authors, funding and licence](#authors-funding-and-licence)

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

**CLEWISE** — *Climate, Land, Energy, Water and Waste, Industry, and Sectoral Emissions* — extends CLEWs in two ways:

| Extension | What it means |
|---|---|
| **Industrial processes module** | Explicit representation of energy-intensive processes, notably cement and aluminium, alongside energy, agriculture and land use, buildings, transport, water and waste |
| **Complete IPCC sectoral emissions** | Accounts for emissions across energy, industrial processes and product use (IPPU), agriculture, forestry and other land use (AFOLU), and waste — so the framework that tracks resource flows also produces an internally consistent GHG inventory |

---

## Model architecture

The model is built in **OSeMOSYS** (Open Source Energy Modelling System) using the **Model User Interface (MUI) v5.5** — a cost-free, bottom-up, linear cost-optimisation environment widely applied to national energy and climate planning.

OSeMOSYS identifies the least-cost combination of technologies and investments that meets exogenously defined demands over a given horizon, subject to technical, resource and policy constraints. Each technology is represented through input/output activity ratios and techno-economic parameters — capital, fixed and variable costs, capacity factors, and operational lifetimes.

### Specification

| Parameter | Value |
|---|---|
| **Modelling framework** | OSeMOSYS, via Model User Interface (MUI) v5.5 |
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

## Scenarios

Three pathways are compared to 2056.

### Business-as-usual (BAU)

The least-cost reference case. Continues historical trends in energy, land and water use with no additional emissions constraint.

### Nationally Determined Contribution (NDC)

Implements Ghana's stated commitments:

- 15% reduction in CO₂eq emissions by 2030 relative to baseline
- Scaled-up renewable capacity — utility-scale and mini-grid solar, small hydropower, wind
- Introduction of nuclear power from 2040
- Public-transport share of trips rising from 64% to 74% by 2030
- Reforestation of approximately 10,000 ha of degraded land per year

### Net zero (NZ)

Builds on the baseline with an emissions limit declining to net-zero CO₂-equivalent emissions by 2056:

- Higher penetration of renewables and nuclear
- Public-transport share rising to approximately 80%
- Widespread replacement of biomass cooking with electric and improved stoves
- Advanced waste treatment infrastructure

---

## The cost–benefit framework

The analytical core is a discounted cost–benefit account comparing each alternative pathway against BAU. For each pathway, the net economic benefit (NEB) is:

```
NEB = PV(operating-cost savings)
    + PV(avoided externalities)
    − PV(additional capital investment)
```

Where operating-cost savings are BAU operating and fuel costs minus those of the pathway; avoided externalities are the valued development co-benefits; and additional capital is the pathway's capital minus BAU. All streams are annual values over 2020–2056, expressed as present values at a real discount rate of 5%. A positive NEB means the savings and avoided damages of a pathway outweigh its additional investment.

The same accounting is applied sector by sector, so the contribution of power, transport, industry, buildings, agriculture and land, water and waste can each be identified.

### Co-benefit module

Capital and operating cost streams come directly from OSeMOSYS outputs. Avoided externalities are valued with a dedicated module covering six categories:

| Category | Valuation basis |
|---|---|
| Indoor air pollution (IAP) | WHO BAR-HAP burden estimates for Ghana; VSL of USD 85,000 |
| Local / ambient air pollution (LAP) | WHO BAR-HAP; IMF valuation data |
| Sanitation | National estimates |
| Solid waste management | National estimates |
| Transport congestion | National estimates |
| Transport accidents | National estimates |

---

## Headline results

> Figures are discounted to 2026 at a 5% real rate unless otherwise stated.

### The economic case

The net-zero pathway delivers a **net economic benefit of USD 59.2 billion by 2056** relative to BAU. The operating-cost savings and avoided externalities it generates outweigh the additional capital it requires.

| Component (NZ vs BAU) | Present value |
|---|---|
| Additional capital investment | −USD 178 billion |
| Operating-cost savings | +USD 129 billion |
| Avoided externality costs | +USD 108 billion |
| **Net economic benefit** | **+USD 59.2 billion** |

The NDC pathway also returns a positive but smaller net benefit of **USD 24.8 billion**, reflecting its more modest ambition.

Decarbonisation in Ghana is therefore not a net economic burden but a net economic gain, once fuel savings and avoided health and congestion damages are counted. The net benefit is unevenly distributed: the largest gains accrue in **transport, health and environment**, driven by fuel and operating savings and by avoided air-pollution damages from cleaner cooking.

Development co-benefits of the NZ pathway alone are equivalent to roughly **4.7% of Ghana's GDP by 2056**, before operating-cost savings are added.

### Investment requirements

Total investment over 2026–2056:

| Scenario | Total investment | Additional vs BAU |
|---|---|---|
| BAU | USD 237.8 billion | — |
| NDC | USD 256.1 billion | USD 18.3 billion |
| NZ | USD 415.9 billion | USD 178 billion |

Transport accounts for the largest share across all scenarios. Additional NZ investment concentrates in power and transport, reflecting large-scale low-carbon generation, electric mobility, expanded public transport and advanced waste treatment.

### Emissions

Total GHG emissions are approximately 52 MtCO₂eq today.

| Scenario | Emissions by 2056 |
|---|---|
| BAU | ~169 MtCO₂eq |
| NDC | ~118 MtCO₂eq |
| NZ | Net zero CO₂eq |

Because hard-to-abate emissions in transport and industry remain positive at 2056, the NZ balance is achieved by offsetting residuals with land-use carbon sinks. Under NZ, total land-use emission savings reach about 57 MtCO₂eq relative to baseline.

### Sectoral transformation

**Power.** Generation rises from 78 PJ in 2020 to approximately 400 PJ (BAU), 410 PJ (NDC) and 712 PJ (NZ) by 2056. Installed capacity expands from 5.67 GW to about 28.5 GW under BAU, which remains dominated by natural gas (over 80% by 2056). From 2045 the NZ scenario is dominated by large and medium hydropower, nuclear, on- and off-grid solar PV and wind; nuclear contributes about 511 PJ, nearly 72% of total generation.

**Buildings.** Total fuel consumption was 146 PJ in 2022, with biomass at 74%, electricity 19.1% and LPG 7%. Residential demand is projected to reach 245 PJ and commercial 62 PJ by 2055. Alternative pathways shift cooking and low-temperature heating from biomass to electricity.

**Industry.** Fuel demand rises from roughly 54 PJ in 2020 to about 316 PJ by 2056 under BAU. Under NZ, natural gas for high-temperature heating falls from about 141 PJ to roughly 17 PJ, and biomass for low-temperature heating from about 54 PJ to near zero. Cement production, about 6.7 Mt in 2020, roughly doubles by 2055; aluminium nearly triples, from 37.6 kt to about 105 kt.

**Transport.** Under BAU, car demand rises from about 37.5 to 251.8 billion passenger-km between 2022 and 2056, with the fleet expanding from roughly 1.7 to 10.5 million vehicles. Transport energy demand climbs from 132 PJ to 464 PJ. Under NZ, strong electrification from around 2035 raises transport electricity demand from under 0.1 PJ in 2020 to about 102 PJ by 2056.

**Water.** Agricultural demand rises from about 0.74 billion m³ (2022) to 3.1 billion m³ (2056); public supply from 0.41 to about 1.2 billion m³. Power-sector cooling water is eliminated under NZ from 2050 with the phase-out of thermal generation — a direct cross-sectoral synergy that single-sector analysis would miss.

**Waste.** Solid waste generation grows from 8.64 Mt (2022) to about 32 Mt (2056) under BAU. A shift to digesters and advanced treatment under NZ cuts solid- and liquid-waste emissions to about 3.5 and 5 MtCO₂eq respectively by 2056.

---

## The dataset

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

## Repository structure

```
.
├── model/                  OSeMOSYS model files (CLEWISE-Ghana)
├── data/
│   ├── raw/                Source data as received from institutions
│   └── processed/          Cleaned, unit-harmonised model inputs
├── results/                Scenario outputs (BAU, NDC, NZ)
├── co-benefits/            Co-benefit assessment module and inputs
├── docs/                   Methodology, data sources, assumptions
└── README.md
```

---

## Getting started

### Requirements

- **OSeMOSYS** — [github.com/OSeMOSYS/OSeMOSYS](https://github.com/OSeMOSYS/OSeMOSYS)
- **Model User Interface (MUI)** v5.5 or later — [github.com/OSeMOSYS/MUIO](https://github.com/OSeMOSYS/MUIO)
- A linear programming solver (GLPK, CBC, CPLEX or Gurobi)

### Running the model

1. Install OSeMOSYS and the MUI following their respective documentation.
2. Load the model file from `model/` into the MUI.
3. Select a scenario configuration from `model/scenarios/`.
4. Run the optimisation. Runtime depends on solver and hardware.
5. Outputs are written in the standard OSeMOSYS results format; reference outputs for comparison are in `results/`.

### Using the data independently

The dataset in `data/` is structured to be readable without OSeMOSYS. Each workbook sheet corresponds to a parameter set, with units and sources documented in `docs/`. Adaptation to other frameworks requires mapping the technology and commodity naming conventions, which are set out in `docs/`.

---

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

If you use this model or dataset, please cite:

> Akpahou, R., Alfstad, T., & Quirós-Tortós, J. *The economic case for net zero in Ghana: an integrated CLEWISE assessment of investment needs, operating savings and development benefits.*

> Akpahou, R., Alfstad, T., & Quirós-Tortós, J. *Integrated System Analysis in Developing Countries: A Techno-economic Dataset for Climate, Land, Energy, and Water system (CLEWs) modelling in Ghana.* Data in Brief.

A `CITATION.cff` file is provided in the repository root.

---

## Authors, funding and licence

**Authors**

Romain Akpahou, Thomas Alfstad, Jairo Quirós-Tortós

STEER Centre, Department of Geography, Loughborough University, Loughborough LE11 3TU, United Kingdom

**Corresponding author:** Jairo Quirós-Tortós — j.quiros@lboro.ac.uk

**Funding**

The CLEWISE assessment was funded by the European Climate Foundation through the 2050 Pathways Platform. Dataset development was funded by the UK Government Foreign, Commonwealth and Development Office and co-funded by Climate Compatible Growth (CCG), a programme bringing together leading research organisations and led from the STEER Centre, Loughborough University. The views expressed here do not necessarily reflect the official policies of the funders.

**Declaration of competing interests**

The authors declare no competing financial interests or personal relationships that could have influenced the work reported here.

**Licence**

See `LICENSE` in the repository root.

---

*The CLEWISE framework and its net-economic-benefit accounting are transferable. They can be applied wherever integrated, development-oriented decarbonisation planning is needed, providing a consistent way to compare the costs, savings and co-benefits of alternative pathways across sectors and countries.*
