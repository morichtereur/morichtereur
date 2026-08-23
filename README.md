## Moritz Richter

Finance and strategy consultant in Zürich — CFO advisory, global business
services, finance transformation. Currently at EY.

I write code because consulting runs on information that arrives a week too late
to change a decision. Most of what's here is an attempt to close that gap:
pipelines that read the market on a schedule, retrieval over financial
reporting, process analysis that turns an operation's own exhaust into a number
someone can act on, and — more recently — models that price a decision rather
than describe it.

I'm not a software engineer by training. Everything below runs, and where a
project makes a claim there is a script that reproduces it.

### GBS and shared services

**[gbs-location-selection](https://github.com/morichtereur/gbs-location-selection)** · [interactive](https://morichtereur.github.io/location-dashboard/)
Where should a shared-services or capability centre go, and how much of that
answer is evidence rather than opinion? 11 cities scored on seven pillars of
public data, then re-scored 10,000 times across every weighting somebody could
have defended. Only **13%** of the original 2,159-posting sample carried any
shared-services signal — the pillar meant to describe GBS was describing
retained finance nine times out of ten. Restricting the population changes which
city leads: Warsaw on a broad finance sample, **Kraków** on GBS and GCC work.
Seven of the 55 city pairs finish closer than 65/35, and those cities share a
band instead of being given invented positions.
`Python` · `NumPy` · `DuckDB` · `JavaScript` · `pytest`

**[gbs-tom-assignment](https://github.com/morichtereur/gbs-tom-assignment)**
A target operating model arrives as four columns on a slide. The expensive part
is not where an activity sits but how often work crosses between columns, and
nobody in the room has measured which activities follow each other. CP-SAT over
a handoff graph measured from the same 1.6M events, with both metrics written
down before the solve. Concentrating purchase-to-pay pays only above **USD 3.38
per handoff** — the top half of the range declared beforehand, not the middle of
it. Cost decides **13 of 29** positions; the other 16 are ties and are left
blank rather than filled in. The work-family classifier ported from
`gbs-agentic-shift` does not transfer: **0% recall** on judgment work, measured
against a gold set rather than inherited.
`Python` · `OR-Tools` · `DuckDB` · `LLM API` · `pytest`

**[gbs-business-case](https://github.com/morichtereur/gbs-business-case)**
What those findings are worth. Baseline measured from the same 1.6M events
instead of estimated in a workshop, with measured facts and assumptions held in
separate files so a reader can see which half of the answer is evidence. Monte
Carlo over the declared ranges, plus a variance decomposition that says which
week of diligence buys the most confidence — **62%** of the variance sits in
assumptions diligence could resolve. At central assumptions the case does
**not** clear the hurdle — NPV −€142,931, 26% odds of a positive result —
because reworked cases average 1.48 touches, not the multi-touch slog usually
assumed.
`Python` · `DuckDB` · `NumPy` · `matplotlib`

**[gbs-agentic-shift](https://github.com/morichtereur/gbs-agentic-shift)**
McKinsey argues agentic AI is turning the GBS talent pyramid into a diamond — a
shrinking transactional base and a new layer managing the "agent force."
Classified 2,110 live GBS and finance-operations postings across ten markets to
test that claim against the market instead of the pitch deck: agent-ops roles
are **2%** of postings, and the transactional base didn't shrink so much as
change employer — 84% transactional at third-party providers versus 38% at
captive functions. A measured 42.9% recall on the agent-ops class makes that 2%
a lower bound rather than a ceiling.
`Python` · `DuckDB` · `LLM API` · `pytest`

### Finance operations and planning

**[p2p-process-mining](https://github.com/morichtereur/p2p-process-mining)**
Process mining on a real 1.6M-event SAP purchase-to-pay log. Only **20%** of
251,734 cases follow the process's own most common path — the rest scatter
across 11,973 variants, three quarters of which occur exactly once. Rework
carries a **19.6-day** median cycle-time penalty, and the expensive rework is
not the common kind. Includes a citation-grounding eval for LLM-written case
narratives: every claim checked against the raw event log rather than judged by
a second model, and 100% of 186 citations traced to a real event. The
interesting split was cost rather than accuracy — Sonnet wrote 2.4x longer
narratives at 3.5x the price with no grounding advantage over Haiku.
`Python` · `DuckDB` · `LLM API` · `matplotlib`

**[fpa-decision-intelligence](https://github.com/morichtereur/fpa-decision-intelligence)** · [live](https://fpa-decision-intelligence.vercel.app)
A driver-based forecast for adidas built from published filings and backtested
on two vintages — FY2023→FY2024 and FY2024→FY2025 — each using the initial
guidance from the prior year's report rather than a figure revised part-way
through the year it describes. It lands closer than a naive extrapolation on all
six metric-year pairs, which is a statement about a weak baseline rather than
about accuracy: both methods undershot in both years, and the FY2024
operating-profit forecast was wrong by 63%. On top of the forecast sits a
decision layer that ranks each driver's exposure against two declared judgements
— how firm the assumption is, and whether management can move it inside the
year. The ranking and the backtest agree without having been tuned to each
other: working capital is the largest error contributor in both years, in
opposite directions.
`Python` · `NumPy` · `FastAPI` · `Next.js` · `LLM API` · `pytest`

**[finance-close-control-agent](https://github.com/morichtereur/finance-close-control-agent)**
Two finance queues — month-end close and invoice-to-pay — on one auditable
spine. Eighteen deterministic control checks over a synthetic ledger, policy
retrieved with document and clause preserved, and a review gate no model can
talk its way past; then twelve deterministic steps ending in a three-way match,
with price and quantity normalised on both sides before anything is compared.
One rule holds across both: no language model touches arithmetic, matching or a
tolerance decision. The module that does the matching imports no provider and
cannot call one, and a test asserts it. A **€46,812** overcharge that a naive
match clears as a 1.09% rounding difference reads as 15.79% once both sides are
normalised to a net price per base unit.
`Python` · `LangChain` · `LlamaIndex` · `AWS Bedrock` · `DuckDB`

### Market and competitive intelligence

**[gbs-intelligence-agent](https://github.com/morichtereur/gbs-intelligence-agent)**
69 RSS feeds across 33 consulting firms, analyst houses and client companies.
The LLM scores every article 0–3 for strategic relevance; only the top tier
reaches the Monday brief, the rest stay searchable in a dashboard. 1,132
articles scored, 30 reached the brief, 16 weekly editions shipped without a
manual step.
`Python` · `LLM API` · `SQLite`

**[dax-intelligence](https://github.com/morichtereur/dax-intelligence)**
Ask one question across 15 DAX 40 annual reports and get an answer with company
and page citations, behind a prompt that will not answer without a source.
Hybrid retrieval — BM25 and dense search unioned, then cross-encoder re-ranked —
a guardrail that re-parses every citation out of the generated prose and checks
it against the excerpts the model was actually given, and confidence bands that
stop a query with no support in the corpus from reaching the model at all.
Retrieval and generation evals: precision@k, recall@k, claim-level faithfulness.
`Python` · `ChromaDB` · `Streamlit` · `pytest`

### How I build

Python, DuckDB, ChromaDB, SQLite, OR-Tools, the LLM API. Where something needs a
UI I mostly write plain HTML — the dashboards are single files you open in a
browser, no server and no build step, which is easier to hand to a colleague.
One project has a real front end, because it needed one.

Where a project makes a claim, there is a script that reproduces it. Where a
claim turned out to be wrong, the correction is in the history rather than
quietly removed.

### Background

MSc Financial Economics, Erasmus University Rotterdam.

[Portfolio](https://morichtereur.github.io/) · [LinkedIn](https://www.linkedin.com/in/moritz-richter-28297119a/)
