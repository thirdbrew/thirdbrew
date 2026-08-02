<h1 align="center">Charlie</h1>

<p align="center">
  <b>Industrial &amp; Systems Engineering @ Georgia Tech</b><br>
  Optimization, simulation, and statistics pointed at real decisions — capital, and warehouses.
</p>

<p align="center">
  <a href="mailto:charlesbmay3@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

### About

I build systems that are structurally capable of telling me I'm wrong.

Most of my work sits where operations research meets money: backtesting engines that
cannot see the future by construction, warehouse models that have to survive a real pick
face, portfolio logic that records its reasoning before the trade rather than after the
outcome. I pre-register what "working" means, then report the result against that bar —
including when the answer is *this doesn't work*.

- Currently: **Global Innovation Intern @ Americold** (summer 2026) — cold-chain logistics, warehouse throughput modeling
- Studying: ISyE at Georgia Tech — LP/MIP, stochastic models, simulation, regression &amp; DOE
- Focus: quantitative finance, operations research, and the testing infrastructure that makes a result worth believing
- Open to: **Summer 2027 quant research / quant dev / data science internships**

---

### Toolkit

**Core**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

**Modeling &amp; analysis**

![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![statsmodels](https://img.shields.io/badge/statsmodels-3B5C86?style=for-the-badge)
![LP / MIP](https://img.shields.io/badge/LP%20%2F%20MIP-B8312F?style=for-the-badge)
![Discrete-Event Simulation](https://img.shields.io/badge/Discrete--Event%20Sim-5C6BC0?style=for-the-badge)

**Engineering**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)
![mypy](https://img.shields.io/badge/mypy-2A6DB2?style=for-the-badge)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)

---

### Selected Work

#### [Realistic Backtesting Engine](https://github.com/thirdbrew/Back-Testing-Engine)

`Python` · `pandas` · `NumPy`

A bar-by-bar equity backtester written so lookahead bias is a structural impossibility
rather than a thing you remember to avoid. There is exactly one place in the engine where
a decision becomes a fill, and it can only act on the previous bar's target. Every fill
pays half-spread, slippage, and commission, all applied adverse to the trader, because
that is the honest direction. Accounting runs on average cost basis with cash as the
single source of truth.

The worked example is a negative result: a naive EMA(5/8) crossover returns **+6.7% over
five years against +134% for buy-and-hold**, with a worse drawdown and a mean daily return
statistically indistinguishable from zero. The repository exists to document that cleanly,
not to sell a strategy.

#### Systematic Portfolio Engine — *private*

`Python` · `pandas` · `SciPy`

Monthly-rebalanced allocation system with cost-aware sizing, per-position stops, and a
decision journal written *before* each trade so the reasoning stays gradeable after the
outcome. Configuration is centralized — limits, floors, and stops live in one file rather
than scattered through the code.

Four consecutive proposed improvements were rejected after failing pre-registered
out-of-sample tests. Keeping those rejections is the point of the design.

---

<p align="center">
  <sub>Performance figures here are backtest output over a stated window, net of stated costs.<br>
  The assumptions are written down — ask me for them.</sub>
</p>
