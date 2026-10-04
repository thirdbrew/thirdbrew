### Hey, I'm Charlie

I'm an Industrial &amp; Systems Engineering student at Georgia Tech. Most of what I build
sits where operations research meets money: optimization, simulation, and statistics
pointed at decisions that cost something if you get them wrong.

The habit that shows up in all of it: I decide what "working" means *before* I run the
test, then report the result against that bar. Sometimes the answer is that my idea
doesn't work. Those results are in my repos too, and they're the ones I learned the most
from.

This summer I was a Global Innovation Intern at Americold, building simulation and
slotting tools for cold-chain warehouse throughput. Outside of that I run a systematic
trading system I've been building and breaking for a while. The research I can publish
is below, with the warehouse work on synthetic data.

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
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![mypy](https://img.shields.io/badge/mypy-2A6DB2?style=flat-square)

---

### Selected work

**[Warehouse Layer-Pick Slotting Engine](https://github.com/thirdbrew/layer-pick-slotting)** &nbsp;·&nbsp; `Python` `discrete-event sim`

Which pallet should occupy which pick face, right now, and what moves next. A rules engine
that emits advisory ADD/REMOVE/WAIT calls against a live floor state, plus a simulator that
replays a full pick day against them. 84 modules, 295 tests, runs end to end on a seeded
synthetic site. The customer feed it was developed against is not in the repository in any
form, at any point in its history. On seed 7 its default policy takes the floor from a **77% dead-slot
rate to 12%**, and the waved layer-pick rate from 26.3% to 40.0%, weighted by the layers
actually waved rather than averaged across hours. The opt-in resupply-rack policy reaches
10% and 48.3%.

Every rule is a pure function over one snapshot, which is what makes attribution possible:
drop one rule, re-run, read what it was worth. That is how I caught the real problem. The
first version I published moved dead slots 40pp and the layer-pick rate by exactly zero,
every hour of the simulated day. The rule that fills a freed face was disabled by default
and gated a second time, so the engine could evict and nothing else. The number I had led
with was the one that couldn't tell.

**[Systematic Trading Research](https://github.com/thirdbrew/systematic-trading-research)** &nbsp;·&nbsp; `Python` `pandas` `SciPy`

A 70/30 equity + managed-futures allocation, a swing sleeve, and the statistical machinery
that decides whether either is worth funding. The pre-registration harness refuses to grade
a hypothesis until its pass/fail bar is committed and pushed, because a bar still sitting in
your working tree can be amended once you've seen the result. Trials are counted and the
significance test is deflated for them.

**Eight hypotheses registered, five graded, all five failed.** They're published with their
registrations and verdicts intact. The one I'd point at first misses its own bar by 0.0057
Sharpe and then argues, against my interest, that the criterion it nearly passed is the
least robust of the three.

**[Cointegration Pairs Study](https://github.com/thirdbrew/coint-pairs-study)** &nbsp;·&nbsp; `Python` `pandas` `NumPy`

Does pairs trading survive honest statistics? On a point-in-time S&P 500 universe (829
tickers, 2011–2026), a naive cointegration screen calls **173,594** pairs significant where
chance alone predicts **122,920**. After Benjamini–Hochberg FDR control 1,446 survive, and
traded out of sample they return Sharpe **−0.25** against a pre-registered bar of 0.50,
and still −0.19 at zero cost.

Each of the three hypotheses was frozen and pushed to a remote before the run that grades it. An adversarial
review then reversed one of the published conclusions: the trading path normalised its
z-score with a statistic computed from the future. The reversal is documented, not patched.

**[Limit Order Book & Market Making](https://github.com/thirdbrew/lob-market-maker)** &nbsp;·&nbsp; `Python` `pytest`

A price-time-priority matching engine, a synthetic market with informed traders in it, and
two market makers compared on a risk/return frontier. **The naive fixed spread dominates
the Avellaneda–Stoikov closed form at 7 of 7 risk levels**, and the P&L decomposition says
why: adverse selection. A-S prices inventory risk, and its derivation contains no informed
traders. 56 tests.

**[Realistic Backtesting Engine](https://github.com/thirdbrew/Back-Testing-Engine)** &nbsp;·&nbsp; `Python` `pandas` `NumPy`

A bar-by-bar equity backtester built so lookahead bias is impossible by construction rather
than by remembering to avoid it. One place in the engine turns a decision into a fill, and
it can only act on the previous bar's target. Every fill pays half-spread, slippage, and
commission, all applied against the trader, which is the honest direction.

I used it on a naive EMA(5/8) crossover. It returned **+6.7% over five years against +134%
for buy-and-hold**, with a worse drawdown and a mean daily return you can't distinguish
from zero. That's the result, and documenting it cleanly was the point.

---

<sub>Performance figures are backtest output over a stated window, net of stated costs.
The assumptions are written down, and I'm happy to walk through them.</sub>

<sub>[charlesbmay3@gmail.com](mailto:charlesbmay3@gmail.com)</sub>
