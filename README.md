## Moritz Richter

Finance and strategy consultant in Zürich — CFO advisory, global business services,
finance transformation. Currently at EY.

I write code because consulting runs on information that arrives a week too late to
change a decision. Most of what's here is an attempt to close that gap: pipelines that
read the market on a schedule, retrieval systems that make a stack of annual reports
answerable in one query.

I'm not a software engineer by training. The projects below run in production anyway.

### Things I've built

**[GBS Intelligence Agent](https://github.com/morichtereur/gbs-intelligence-agent)**
69 RSS feeds covering 33 consulting firms, analyst houses, and client companies.
Claude scores every article 0–3 for strategic relevance; only the 3s reach the
newsletter, the rest stay in the dashboard. 1,600 articles ingested, 16 weekly
editions shipped so far. It runs Monday morning on a timer, mails itself, and
archives by calendar week — no step in that chain is manual.

**[DAX Intelligence](https://github.com/morichtereur/dax-intelligence)**
Ask one question across 15 DAX 40 annual reports, get an answer with company and page
citations. ChromaDB retrieval into Claude Sonnet, behind a system prompt that won't
answer without a source. Chunking is word-based at 800/100 rather than character-based,
because German annual report layouts break character splitters in ways that are
tedious to debug.

**[P2P Process Mining](https://github.com/morichtereur/p2p-process-mining)**
251,734 real purchase orders (BPI Challenge 2019), reconstructed into a directly-follows
process map with DuckDB and networkx. Only 20% of cases follow the process's own most
common path; rework carries a 19.6-day cycle-time penalty that turns out to have no
correlation with how often it fires. The one control the system actually enforces —
invoice verification gated on goods receipt — holds with zero exceptions across 11,076
cases; the one it doesn't holds up 1.6% of the time.

**[R2R Process Mining](https://github.com/morichtereur/r2r-process-mining)**
Same four-step method, aimed at record-to-report instead — except no public GL log
exists to mine, for the obvious reason that it's what an audit would want to see. So
this one builds its own: 27,264 journal entries with maker-checker, reconciliation
breaks, and intercompany elimination baked in on purpose, then independently
rediscovered from the raw event data. Maker-checker holds with zero exceptions across
6,548 cases; post-close entries slip through 1.30% of the time, at nearly 15x the rate
for manual entries versus automated sub-ledger feeds.

### How I build

Python, Claude API, DuckDB, ChromaDB, SQLite, Streamlit, Power BI. Where something needs a UI
I tend to write plain HTML — both dashboards are single files you open in a browser,
no server, no build step. Easier to hand to a colleague that way.

### Elsewhere

[Portfolio](https://morichtereur.github.io/) · [LinkedIn](https://www.linkedin.com/in/moritz-richter-28297119a/)

MSc Financial Economics, Erasmus University Rotterdam.
