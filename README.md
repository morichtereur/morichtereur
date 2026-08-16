## Moritz Richter

Finance and strategy consultant in Zürich — CFO advisory, global business
services, finance transformation. Currently at EY.

I write code because consulting runs on information that arrives a week too late
to change a decision. Most of what's here is an attempt to close that gap:
pipelines that read the market on a schedule, retrieval over financial
reporting, and process analysis that turns an operation's own exhaust into a
number someone can act on.

I'm not a software engineer by training. The projects below run in production
anyway.

### Things I've built

**[p2p-process-mining](https://github.com/morichtereur/p2p-process-mining)**
Process mining on a real 1.6M-event SAP purchase-to-pay log. Only 20% of 251,734
cases follow the process's own most common path — the rest scatter across 11,973
variants. Rework carries a 19.6-day median cycle-time penalty, and the expensive
rework is not the common kind. Includes a citation-grounding eval for LLM-written
case narratives: every claim checked against the raw event log rather than judged
by a second model.
`Python` · `DuckDB` · `LLM API` · `matplotlib`

**[gbs-business-case](https://github.com/morichtereur/gbs-business-case)**
The other half of the same problem: what those findings are worth. Baseline
measured from the same 1.6M events instead of estimated in a workshop, with
measured facts and assumptions held in separate files so a reader can see which
half of the answer is evidence. Monte Carlo over the declared ranges, plus a
variance decomposition that says which week of diligence buys the most
confidence. At central assumptions the case does **not** clear the hurdle —
NPV −€142,931, 26% odds of a positive result — because reworked cases average
1.48 touches, not the multi-touch slog usually assumed.
`Python` · `DuckDB` · `NumPy` · `matplotlib`

**[gbs-intelligence-agent](https://github.com/morichtereur/gbs-intelligence-agent)**
69 RSS feeds across 33 consulting firms, analyst houses and client companies.
The LLM scores every article 0–3 for strategic relevance; only the top tier
reaches the Monday brief, the rest stay searchable in a dashboard. 1,132 articles
scored, 30 reached the brief, 16 weekly editions shipped without a manual step.
`Python` · `LLM API` · `SQLite`

**[dax-intelligence](https://github.com/morichtereur/dax-intelligence)**
Ask one question across 15 DAX 40 annual reports, get an answer with company and
page citations, behind a prompt that will not answer without a source. Retrieval
and generation eval harness: precision@k / recall@k, faithfulness, citation
accuracy.
`Python` · `ChromaDB` · `Streamlit` · `pytest`

### How I build

Python, DuckDB, ChromaDB, SQLite, the LLM API. Where something needs a UI I
tend to write plain HTML — the dashboards are single files you open in a browser,
no server, no build step. Easier to hand to a colleague that way.

Where a project makes a claim, there is a script that reproduces it.

### Background

MSc Financial Economics, Erasmus University Rotterdam.

[Portfolio](https://morichtereur.github.io/) · [LinkedIn](https://www.linkedin.com/in/moritz-richter-28297119a/)
