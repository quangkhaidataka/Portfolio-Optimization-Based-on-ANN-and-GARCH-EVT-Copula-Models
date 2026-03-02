# 📈 Portfolio Optimization Based on ANN and GARCH-EVT-Copula Models

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=flat-square&logo=jupyter)
![Domain](https://img.shields.io/badge/Domain-Quantitative%20Finance-purple?style=flat-square)
![Published](https://img.shields.io/badge/Published-World%20Scientific-red?style=flat-square)

> 📄 **This repository contains the official implementation code for the published research paper:**
>
> **"Portfolio Optimization Based on Artificial Neural Network and GARCH-EVT-Copula Models"**
> *International Journal of Uncertainty, Fuzziness and Knowledge-Based Systems — World Scientific*
> 🔗 [Read the paper](https://www.worldscientific.com/doi/abs/10.1142/S0218488523400184)

---

## 📌 Overview

Accurately modeling financial risk is one of the central challenges in quantitative finance. Traditional risk models such as historical simulation or variance-covariance approaches often fail to capture the fat-tailed, asymmetric, and nonlinear dynamics inherent in real-world financial return series — particularly during periods of market stress.

This project presents a novel hybrid framework that combines:

- **Artificial Neural Networks (ANN)** for forecasting stock return directions
- **GARCH models** for capturing volatility clustering in financial time series
- **Extreme Value Theory (EVT)** for modeling tail risk beyond the normal distribution
- **Copula functions** for modeling non-linear dependence structures between assets

Together, these components power a robust **portfolio optimization pipeline** applied to **Asian stock markets**, with portfolio weights determined by minimizing the portfolio's **Value-at-Risk (VaR)**.

---

## 🎯 Research Objectives

- Propose a hybrid ANN + GARCH-EVT-Copula framework for portfolio risk modeling
- Model the marginal distribution of each asset's returns using GARCH-EVT
- Capture joint dependence between assets using Copula models
- Predict return directions using Artificial Neural Networks
- Optimize portfolio weights by minimizing VaR
- Benchmark performance against traditional portfolio optimization methods

---

## 🔬 Methodology

The research pipeline is structured in five sequential stages, each corresponding to a dedicated notebook:

### Stage 1 — Data Collection & Preprocessing (`FIRST RUN ALL STOCKS ASIA.ipynb`)
- Collects historical price data for Asian market stocks
- Computes log returns and performs stationarity tests
- Conducts preliminary statistical analysis (skewness, kurtosis, autocorrelation)

### Stage 2 — GARCH Fitting & Standardized Residuals (`SECOND CALCULATE STANDARDIZED RESIDUAL.ipynb`)
- Fits GARCH-family models (GARCH, EGARCH, GJR-GARCH) to each asset's return series
- Extracts standardized residuals for use in EVT and Copula modeling
- Selects the best-fitting GARCH specification per asset

### Stage 3 — VaR Estimation & Comparison (`THIRD COMPARE VAR PREDICTION THESIS.ipynb`)
- Applies Extreme Value Theory (EVT) via Peaks-Over-Threshold (POT) to model tail risk
- Estimates portfolio-level Value-at-Risk (VaR) and Conditional VaR (CVaR)
- Compares VaR predictions across different models (Historical, Parametric, GARCH-EVT)
- Performs backtesting to evaluate prediction accuracy

### Stage 4 — Copula & Portfolio Construction (`FOURTH PORT DEMO.ipynb`)
- Fits Copula models (Gaussian, Student-t, Clayton, Gumbel, Frank) to capture asset dependence
- Selects optimal Copula based on goodness-of-fit criteria
- Constructs candidate portfolios using Monte Carlo simulation

### Stage 5 — ANN-Based Weight Allocation (`FIFTH WEIGHT ALLOCATION.ipynb`)
- Trains an Artificial Neural Network to predict stock return signals
- Integrates ANN predictions with the GARCH-EVT-Copula risk framework
- Determines final optimal portfolio weights by minimizing VaR subject to return constraints

---

## 🛠️ Tech Stack

| Category | Libraries |
|---|---|
| Language | Python 3.8+ |
| Environment | Jupyter Notebook |
| Data Handling | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn` |
| Statistical Modeling | `statsmodels`, `scipy` |
| GARCH Modeling | `arch` |
| Deep Learning | `tensorflow` / `keras` |
| Copula Modeling | `copulas`, `scipy` |
| Optimization | `scipy.optimize`, `cvxpy` |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- `pip` package manager

### 1. Clone the Repository

```bash
git clone https://github.com/quangkhaidataka/Portfolio-Optimization-Based-on-ANN-and-GARCH-EVT-Copula-Models.git
cd Portfolio-Optimization-Based-on-ANN-and-GARCH-EVT-Copula-Models
```

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn statsmodels scipy arch tensorflow keras cvxpy jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 5. Run the Pipeline in Order

The notebooks are designed to be executed **sequentially**. Run them in the following order:

| Step | Notebook | Description |
|------|----------|-------------|
| 1 | `FIRST RUN ALL STOCKS ASIA.ipynb` | Data collection & preprocessing |
| 2 | `SECOND CALCULATE STANDARDIZED RESIDUAL.ipynb` | GARCH fitting & residuals |
| 3 | `THIRD COMPARE VAR PREDICTION THESIS.ipynb` | VaR estimation & comparison |
| 4 | `FOURTH PORT DEMO.ipynb` | Copula fitting & portfolio construction |
| 5 | `FIFTH WEIGHT ALLOCATION.ipynb` | ANN-based weight allocation |

> ⚠️ **Important:** Each notebook may depend on outputs (data files, model objects) generated by the preceding notebook. Always run them in the order listed above.

---

## 📁 Project Structure

```
Portfolio-Optimization-Based-on-ANN-and-GARCH-EVT-Copula-Models/
│
├── FIRST RUN ALL STOCKS ASIA.ipynb              # Stage 1: Data preprocessing
├── SECOND CALCULATE STANDARDIZED RESIDUAL.ipynb # Stage 2: GARCH modeling
├── THIRD COMPARE VAR PREDICTION THESIS.ipynb    # Stage 3: VaR estimation
├── FOURTH PORT DEMO.ipynb                       # Stage 4: Copula & portfolio
├── FIFTH WEIGHT ALLOCATION.ipynb                # Stage 5: ANN weight allocation
└── README.md                                    # Project documentation
```

---

## 📚 Citation

If you use this code in your research, please cite the original paper:

```bibtex
@article{portfolio_ann_garch_evt_copula,
  title     = {Portfolio Optimization Based on Artificial Neural Network and GARCH-EVT-Copula Models},
  journal   = {International Journal of Uncertainty, Fuzziness and Knowledge-Based Systems},
  publisher = {World Scientific},
  doi       = {10.1142/S0218488523400184},
  url       = {https://www.worldscientific.com/doi/abs/10.1142/S0218488523400184}
}
```

---

## 🤝 Contributing

Contributions and discussion are welcome. Feel free to open an issue for questions related to the methodology or implementation, or submit a pull request for improvements.

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Quang Khai**
- GitHub: [@quangkhaidataka](https://github.com/quangkhaidataka)
- Published Paper: [World Scientific — IJUFKS](https://www.worldscientific.com/doi/abs/10.1142/S0218488523400184)
