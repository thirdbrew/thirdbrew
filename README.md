<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img alt="Charlie — Industrial and Systems Engineering, Georgia Tech" src="assets/banner-light.svg" width="100%">
</picture>

### Hey, I'm Charlie

I'm an Industrial &amp; Systems Engineering student at Georgia Tech. A lot of what I build
sits where operations research meets money — optimization, simulation, and statistics
pointed at decisions that actually cost something if you get them wrong. The rest is
games, tooling, and whatever else I want to understand well enough to measure.

The habit that shows up in all of it: I decide what "working" means *before* I run the
test, then report the result against that bar. Sometimes the answer is that my idea
doesn't work. Those results are in my repos too — they're the ones I learned the most
from.

Right now I'm a **Global Innovation Intern at Americold**, working on cold-chain
logistics and warehouse throughput. Outside of that I run a systematic trading system
I've been building and breaking for a while. The parts of both that are safe to publish
are below, on synthetic data where the real feed can't travel.

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
![Godot](https://img.shields.io/badge/Godot-478CBF?style=flat-square&logo=godotengine&logoColor=white)

---

### Selected work

**[Warehouse Layer-Pick Slotting Engine](https://github.com/thirdbrew/layer-pick-slotting-engine)** &nbsp;·&nbsp; `Python` `discrete-event sim`

Which pallet should occupy which pick face, right now, and what moves next. A rules engine
that emits advisory ADD/REMOVE/WAIT calls against a live floor state, plus a simulator that
replays a full pick day against them. 85 modules, 294 tests, runs end to end on a seeded
synthetic site — the customer feed it was developed against is not in the repository in any
form, at any point in its history.

Every rule is a pure function over one snapshot, which is what makes attribution possible:
drop one rule, re-run, read what it was worth. Doing that turned up the thing I'd have
missed otherwise. The floor's dead-slot rate improves 42pp, and **almost all of that comes
from eviction, which moves the layer-pick rate by nothing at all.** The two are separate
rules doing separate jobs. Reporting the number that looked good would have shipped an
engine that could not pick any faster than the floor it replaced.

**[Realistic Backtesting Engine](https://github.com/thirdbrew/Back-Testing-Engine)** &nbsp;·&nbsp; `Python` `pandas` `NumPy`

A bar-by-bar equity backtester built so lookahead bias is impossible by construction
rather than by remembering to avoid it. One place in the engine turns a decision into a
fill, and it can only act on the previous bar's target. Every fill pays half-spread,
slippage, and commission, all applied against the trader — the honest direction.

I used it on a naive EMA(5/8) crossover. It returned **+6.7% over five years against
+134% for buy-and-hold**, with a worse drawdown and a mean daily return you can't
distinguish from zero. That's the result, and documenting it cleanly was the point.

**[Systematic Trading Research](https://github.com/thirdbrew/systematic-trading-research)** &nbsp;·&nbsp; `Python` `pandas` `SciPy`

A 70/30 equity + managed-futures allocation, a swing sleeve, and the statistical machinery
that decides whether either is worth funding. The pre-registration harness refuses to grade
a hypothesis until its pass/fail bar is committed and pushed, because a bar still sitting in
your working tree can be amended once you've seen the result. Trials are counted and the
significance test is deflated for them.

**Eight hypotheses registered, five graded, all five FAIL** — published with their
registrations and verdicts intact. The one I'd point at first misses its own bar by 0.0057
Sharpe and then argues, against my interest, that the criterion it nearly passed is the
least robust of the three.

---

### Same habit, other places

I keep noticing the same pattern in my own work: I end up building the thing that tells
me whether the thing works. It shows up well outside finance.

**Hearthwake** &nbsp;·&nbsp; *local* &nbsp;·&nbsp; `Godot 4.7` `GDScript`

A fishing game that started as a bake-off. Three candidate mechanics live in one gray-box
scene at the same time — press 1, 2, or 3 to swap between them mid-session, hold-and-release
against pulse against tap. The point is to feel all three back to back instead of arguing
about them.

I don't tune game feel in a test harness. Feel isn't a number, so the build gets played and
judged by hand — agents can build it, but they can't tell me whether casting feels good.

**Vault tooling** &nbsp;·&nbsp; *local* &nbsp;·&nbsp; `Python`

A personal knowledge system with a query layer instead of a folder tree — ask it a question
in plain language and it points at the one section that answers it. What I like most is the
part that grades it: an eval harness that runs natural-language questions against a holdout
set and scores retrieval on recall@k and MRR. When search gets worse, the numbers tell me,
instead of me quietly failing to find things.

**Workflow tooling** &nbsp;·&nbsp; `Python` `Markdown`

A dozen or so custom Claude Code skills and hooks for the things I do repeatedly: staging a
trade with a checklist that refuses to write the order until every question is answered,
reconciling fills across every file that a single fill touches, closing out a work session
into the vault. Mostly guardrails I built after getting something wrong once.

---

<sub>Performance figures are backtest output over a stated window, net of stated costs.
The assumptions are written down — ask me for them.</sub>

<sub>📫 &nbsp;[charlesbmay3@gmail.com](mailto:charlesbmay3@gmail.com)</sub>
