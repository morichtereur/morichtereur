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

### How I build

Python, Claude API, ChromaDB, SQLite, Streamlit, Power BI. Where something needs a UI
I tend to write plain HTML — both dashboards are single files you open in a browser,
no server, no build step. Easier to hand to a colleague that way.

### Elsewhere

[Portfolio](https://morichtereur.github.io/) · [LinkedIn](https://www.linkedin.com/in/moritz-richter-28297119a/)

MSc Financial Economics, Erasmus University Rotterdam.
