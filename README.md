# EconSSI
### Physics-Informed Systemic Stress Intelligence for Financial Markets

EconSSI is an open-source, research-oriented framework for **systemic risk monitoring and forecasting**
that integrates **econophysics**, **network theory**, **critical phenomena**, and **deep learning** to model market-wide stress regimes.

Unlike traditional approaches that focus on short-horizon event prediction only, EconSSI emphasizes **regime-level stress dynamics** and **early-warning signals**.

---

## Project Status

- ✅ Full research pipeline implemented in: `notebooks/SystemicStressLab.ipynb`
- ✅ Dashboard prototype notebook prepared in: `notebooks/Streamlit_Dashboard.ipynb`
- ⏳ Streamlit deployment (public link) planned as a next step

---

## Core Methodology

EconSSI combines multiple physics-inspired layers:

- **Network Contagion**
  - Rolling correlation networks + eigenvalue concentration (λ₁ ratio)
  - Graph topology metrics (clustering, centralization)

- **Critical Slowing Down (CSD)**
  - Rolling AR(1), variance, and autocorrelation on market mode proxies

- **Multifractality (MFDFA)**
  - Periodic multifractal analysis (ΔH) for regime characterization

- **Ising / Spin-Glass Proxies**
  - Magnetization and susceptibility-style herding indicators

- **Systemic Stress Index (SSI)**
  - Interpretable composite index from standardized physics features

- **Agent-Based Modeling (ABM)**
  - Liquidity shock simulation + early-warning proxy signals

- **Deep Learning (LSTM)**
  - Multi-task forecasting:
    - Regression: forecast future systemic stress level (SSI(t+H))
    - Classification: forecast future crisis probability

---

## Key Message

> **Physics-informed features improve regime-level stress forecasting,  
> while event-level crisis classification remains intrinsically difficult  
> under extreme class imbalance.**

This framework is best interpreted as a **monitoring and early-warning** system rather than a crash-date oracle.

---

## How to Interpret Results (Non-Technical)

### 1) SSI = “Stress Level” (Regime Indicator)
- Think of SSI as a **thermometer** for the market’s overall fragility.
- High SSI means the system is **more vulnerable**, not that a crash must happen tomorrow.

### 2) Crisis Probability = “Event Risk” (Rare Outcomes)
- Crises are rare → probabilities can look small even when risk is building.
- In rare-event settings, **calibration (e.g., Brier score)** can be more informative than PR-AUC alone.

### 3) Why a model can be “right” even with low PR-AUC
- Predicting *exact crisis events* is inherently difficult because:
  - labels are rare,
  - regimes shift,
  - market microstructure and exogenous shocks dominate event timing.

---

## Data, Privacy, and Security

- Data sources are **publicly available financial time series** (e.g., ETF prices/returns).
- This repository does **not** include:
  - personal data,
  - sensitive information,
  - proprietary datasets.
- If you export derived artifacts (e.g., `df_test.csv`) for dashboards, ensure they contain **no private information** and are safe to publish.

---

## Quickstart

### Option A — Run the full pipeline (research notebook)
Open:
- `notebooks/SystemicStressLab.ipynb`

Recommended environment:
- Python 3.10+
- GPU optional (A100 supported)

### Option B — Run the dashboard prototype notebook
Open:
- `notebooks/Streamlit_Dashboard.ipynb`

(Deployment instructions will be added once the Streamlit app is finalized.)

---

## License

You may use, modify, and distribute with attribution.

---

## Citation

If you use EconSSI in academic work, please cite:

**EconSSI: Physics-Informed Systemic Stress Intelligence for Financial Markets**  
Author: Meriç Özcan

---

## Author

**Meriç Özcan**  
Statistics Student & Quantitative Risk Researcher
