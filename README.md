<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img alt="Charlie — Industrial and Systems Engineering, Georgia Tech" src="assets/banner-light.svg" width="100%">
</picture>

### Hey, I'm Charlie

I'm an Industrial &amp; Systems Engineering student at Georgia Tech, and most of what I
build lives where operations research meets money — optimization, simulation, and
statistics pointed at decisions that actually cost something if you get them wrong.

The habit that shows up in all of it: I decide what "working" means *before* I run the
test, then report the result against that bar. Sometimes the answer is that my idea
doesn't work. Those results are in my repos too — they're the ones I learned the most
from.

Right now I'm a **Global Innovation Intern at Americold**, working on cold-chain
logistics and warehouse throughput. Outside of that I run a systematic trading system
I've been building and breaking for a while, and I'm slowly getting the parts of it that
are safe to share out into the open.

**Looking for:** summer 2027 internships in quant research, quant dev, or data science.

---

### What I work with

**Core**
&nbsp;
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

**Modeling**
&nbsp;
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white)
![statsmodels](https://img.shields.io/badge/statsmodels-3B5C86?style=flat-square)
![LP / MIP](https://img.shields.io/badge/LP_%2F_MIP-B8312F?style=flat-square)
![Discrete-Event Sim](https://img.shields.io/badge/Discrete--Event_Sim-5C6BC0?style=flat-square)

**Engineering**
&nbsp;
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![mypy](https://img.shields.io/badge/mypy-2A6DB2?style=flat-square)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)

---

### Selected work

**[Realistic Backtesting Engine](https://github.com/thirdbrew/Back-Testing-Engine)** &nbsp;·&nbsp; `Python` `pandas` `NumPy`

A bar-by-bar equity backtester built so lookahead bias is impossible by construction
rather than by remembering to avoid it. One place in the engine turns a decision into a
fill, and it can only act on the previous bar's target. Every fill pays half-spread,
slippage, and commission, all applied against the trader — the honest direction.

I used it on a naive EMA(5/8) crossover. It returned **+6.7% over five years against
+134% for buy-and-hold**, with a worse drawdown and a mean daily return you can't
distinguish from zero. That's the result, and documenting it cleanly was the point.

**Systematic Portfolio Engine** &nbsp;·&nbsp; *private* &nbsp;·&nbsp; `Python` `pandas` `SciPy`

Monthly-rebalanced allocation system with cost-aware sizing, per-position stops, and a
decision journal I write *before* each trade so the reasoning is still gradeable after I
know the outcome. Limits, floors, and stops live in one config file instead of scattered
through the code.

Four improvements I was convinced would work got rejected after failing pre-registered
out-of-sample tests. I kept the write-ups.

---

<sub>Performance figures are backtest output over a stated window, net of stated costs.
The assumptions are written down — ask me for them.</sub>

<sub>📫 &nbsp;[charlesbmay3@gmail.com](mailto:charlesbmay3@gmail.com)</sub>
