# EconSSI  
### Physics-Informed Systemic Stress Intelligence for Financial Markets

EconSSI is an open-source, research-oriented framework for **systemic risk monitoring and forecasting**  
that integrates **econophysics**, **network theory**, **critical phenomena**, and **deep learning** to model market-wide stress regimes.

Unlike traditional approaches that focus on short-horizon event prediction only, EconSSI emphasizes **regime-level stress dynamics** and **early-warning signals**.

---

## Project Status

- ✅ Full research pipeline implemented in: `SystemicStressLab_EconSSI.ipynb`
- ✅ Dashboard prototype notebook prepared in: `Html_Dashboard_EconSSI.ipynb`
- ✅ Static HTML research report generated: `econssi_report.html`
- ⏳ Streamlit deployment (public link) planned as a next step

---

## System Architecture (High-Level)

EconSSI follows a modular, physics-informed pipeline designed to track the evolution of systemic fragility rather than predicting single crash dates.

```mermaid
flowchart TD

A[Raw Market Data - Prices and Returns]
B[Market Mode Extraction - Rolling Returns and Correlations]

C1[Network Contagion - Correlation Networks and Lambda1]
C2[Critical Slowing Down - AR1 Variance Autocorrelation]
C3[Multifractality - MFDFA and DeltaH]
C4[Herding Proxies - Ising Spin Glass]

D[Systemic Stress Index SSI]

E1[LSTM Forecasting - Future SSI and Crisis Probability]
E2[Agent Based Modeling - Liquidity Shock Simulation]

F[Monitoring and Decision Support - Dashboard and Early Warning]

A --> B

B --> C1
B --> C2
B --> C3
B --> C4

C1 --> D
C2 --> D
C3 --> D
C4 --> D

D --> E1
D --> E2

E1 --> F
E2 --> F

```
This architecture prioritizes **regime detection and stress accumulation** over short-horizon crash timing.

---

## Core Methodology

EconSSI combines multiple physics-inspired layers:

- **Network Contagion**
  - Rolling correlation networks and eigenvalue concentration (λ₁ ratio)
  - Graph topology metrics (clustering, centralization)

- **Critical Slowing Down (CSD)**
  - Rolling AR(1), variance, and autocorrelation on market mode proxies

- **Multifractality (MFDFA)**
  - Periodic multifractal analysis (ΔH) for regime characterization

- **Ising / Spin-Glass Proxies**
  - Magnetization and susceptibility-style herding indicators

- **Systemic Stress Index (SSI)**
  - Interpretable composite index built from standardized physics-based features

- **Agent-Based Modeling (ABM)**
  - Liquidity shock simulations and early-warning proxy signals

- **Deep Learning (LSTM)**
  - Multi-task forecasting:
    - Regression: forecast future systemic stress level (SSI(t+H))
    - Classification: forecast future crisis probability

---

## Key Message

> **Physics-informed features improve regime-level stress forecasting,  
> while event-level crisis classification remains intrinsically difficult  
> under extreme class imbalance.**

This framework should be interpreted as a **monitoring and early-warning system**,  
not a deterministic crash-date oracle.

---

## Why Brier Score instead of PR-AUC?

Crisis prediction in financial markets is an **extreme rare-event problem** with strong class imbalance.

In such settings:

- **PR-AUC** primarily measures ranking performance,
- but does not sufficiently capture the **quality of probability calibration**.

**Brier Score**, on the other hand:
- directly measures the squared error between predicted probabilities and realized outcomes,
- evaluates how *well-calibrated* the risk estimates are,
- is more informative for **early-warning and risk monitoring systems**.

In EconSSI, crisis probabilities are not interpreted as alarms,  
but as **gradual indicators of risk accumulation**.

A model can therefore exhibit:
- low PR-AUC (poor event timing),
- but a strong Brier Score (accurate risk calibration at the regime level).

This is consistent with the project’s goal of **systemic fragility monitoring**, not exact crash prediction.

---

## How to Interpret Results (Non-Technical)

### 1) SSI = “Stress Level” (Regime Indicator)
- Think of SSI as a **thermometer** for overall market fragility.
- High SSI means the system is **more vulnerable**, not that a crash must happen immediately.

### 2) Crisis Probability = “Event Risk” (Rare Outcomes)
- Crises are rare; probabilities may appear small even when risk is building.
- Calibration metrics (e.g., Brier Score) are often more meaningful than classification accuracy.

### 3) Why a model can be “right” with low PR-AUC
- Crisis timing is dominated by:
  - regime shifts,
  - exogenous shocks,
  - market microstructure effects.
- The model’s strength lies in **risk buildup detection**, not event timing precision.

---

## Data, Privacy, and Security

- Data sources consist of **publicly available financial time series** (e.g., ETF prices and returns).
- This repository does **not** include:
  - personal data,
  - sensitive information,
  - proprietary datasets.
- If exporting derived artifacts (e.g., `df_test.csv`) for dashboards, ensure they contain **no private or sensitive information**.

---

## Quickstart

### Option A — Run the full research pipeline
Open:
- `SystemicStressLab_EconSSI.ipynb`

Recommended environment:
- Python 3.10+
- GPU optional (A100 supported)

### Option B — Run the dashboard prototype
Open:
- `Html_Dashboard_EconSSI.ipynb`

### Option C — View static research report
Open:
- `econssi_report.html`

---

## License

You may use, modify, and distribute this work **with attribution**.

---

## Citation

If you use EconSSI in academic work, please cite:

**EconSSI: Physics-Informed Systemic Stress Intelligence for Financial Markets**  
Author: Meriç Özcan

---

## Author

**Meriç Özcan**  
Statistics Student & Quantitative Risk Researcher
