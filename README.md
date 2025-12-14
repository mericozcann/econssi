# SystemicStressLab
Econophysics-Based Systemic Risk Forecasting Model for Financial Markets  
**Physics-informed early-warning signals + network contagion + (optional) deep forecasting** in a single reproducible notebook.

## Overview
SystemicStressLab is an educational and research-oriented prototype that models systemic financial risk beyond classical econometrics by combining:

- Dynamic correlation networks and contagion proxies (graph metrics, market mode locking via λ1 ratio)
- Econophysics-inspired early-warning indicators (critical slowing down: AR(1), variance, ACF1)
- Multifractal analysis via periodic MFDFA (ΔH as multifractality strength)
- Ising/spin-glass proxies (magnetization |m|, susceptibility proxy, coupling strength from correlations)
- A unified **Systemic Stress Index (SSI)** for regime monitoring
- Optional stress sandbox via a minimal **Agent-Based Model (ABM)**
- Optional multi-task **LSTM forecasting**: predict future SSI and crisis probability

This repository is intended for **research prototyping, demonstration, and learning**.

## Key Outputs
- **SSI time-series dashboard** (0–1 scale) with crisis labels
- **Physics vs non-physics ablation** (baseline logistic model)
- Optional: ABM stress scenario visualization
- Optional: LSTM-based multi-task forecasts (SSI(t+h), crisis probability)

## Repository Structure
Recommended structure:
- `notebooks/`
  - `SystemicStressLab_Demo.ipynb`  (main Colab notebook)
- `src/` (optional; if you later modularize)
- `requirements.txt`
- `LICENSE`

## Quickstart (Google Colab)
1. Open the notebook in Colab.
2. Run the install cell.
3. Run cells sequentially top-to-bottom.

**Default configuration** uses a small ETF basket:
`SPY, QQQ, XLF, XLE, XLK, XLV, TLT, HYG, LQD`

You may adjust:
- ticker universe
- rolling window
- forecast horizon
- crisis label threshold

## Method Summary (High-Level)
1. **Data Hub**
   - Downloads OHLCV data (default: Yahoo Finance via `yfinance`)
   - Computes returns and classic risk proxies (e.g., realized volatility)

2. **Network Layer**
   - Rolling correlation matrices with Ledoit–Wolf shrinkage
   - Graph metrics + λ1 ratio (market mode locking proxy)

3. **Econophysics Signals**
   - Critical slowing down metrics (AR(1), variance, ACF1)
   - Periodic MFDFA: multifractality strength (ΔH)

4. **Ising/Spin-Glass Proxies**
   - Binarized return spins
   - Magnetization |m| and susceptibility proxy
   - Coupling matrix J derived from correlation mapping

5. **SSI Construction**
   - Standardizes features and aggregates into a bounded (0–1) stress index

6. **(Optional) Learning Layer**
   - Baseline classification ablation: classic-only vs classic+physics
   - LSTM multi-task forecasting for proactive risk prediction

## Legal, Privacy, and Security Notes
### No financial advice
This project is provided **for educational and research purposes only** and does **not** constitute financial, investment, legal, or tax advice. You are solely responsible for how you use the outputs.

### Data sources and licensing
By default, the notebook may download market data from third-party providers (e.g., Yahoo Finance via `yfinance`).
You are responsible for complying with each provider’s terms of use and data licensing restrictions.

### Privacy and sensitive data
- This repository is designed to run on **public market data**.  
- Do **not** upload or commit sensitive or regulated data (e.g., customer PII, bank transaction logs, account identifiers, credentials, API keys).
- If you adapt the pipeline to private datasets, ensure you follow relevant privacy laws and institutional policies (e.g., GDPR/KVKK where applicable), and implement data minimization, access controls, and secure storage.

### Security best practices
- Do not hardcode secrets in notebooks. Use environment variables or secret managers.
- Review dependencies for known vulnerabilities and keep them updated.
- Treat generated artifacts (plots, logs, exports) as potentially sensitive if they contain proprietary inputs.

## Reproducibility
- Random seeds are set for key libraries where applicable.
- Use a fixed date range and pinned dependency versions in `requirements.txt` for strict reproducibility.

## Limitations
- The “crisis” label is a heuristic rule based on forward returns; it is not a definitive ground truth.
- Econophysics proxies here are simplified for demo use; they may require more rigorous calibration/validation for publication-grade results.
- MFDFA is computed periodically for performance; full rolling MFDFA is heavier.

## Contributing
Contributions are welcome:
- add rigorous Ising parameter estimation (pseudo-likelihood, time-varying couplings)
- implement transformer forecasting and proper probabilistic calibration
- add lead-time and false-alarm operational metrics
- modularize notebook into `src/`

## License
This project is released under an open-source license. See `LICENSE`.
