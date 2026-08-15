# Moritz Richter

**AI Engineer — LLM systems: RAG, retrieval, and evals.**
Finance domain: CFO advisory, GBS, and finance transformation at EY.

I build retrieval-augmented systems and the evaluation harnesses that keep them
honest — measured, provider-swappable, and actually shipped. Finance is the
domain edge, not a footnote.

### Selected work

**[dax-intelligence](https://github.com/morichtereur/dax-intelligence)** — RAG over 15 DAX 40 annual reports with page-level citations, plus a retrieval + generation eval harness: precision@k / recall@k, faithfulness, and citation accuracy. Backend-agnostic harness, judge model configurable — implemented on the Claude API.
`Python` · `ChromaDB` · `Streamlit` · `pytest` · `GitHub Actions`

**[gbs-intelligence-agent](https://github.com/morichtereur/gbs-intelligence-agent)** — Automated competitor & client intelligence: 69 RSS feeds → LLM relevance scoring → weekly newsletter + interactive dashboard.
`Python` · `LLM API` · `SQLite`

**[p2p-process-mining](https://github.com/morichtereur/p2p-process-mining)** — Process mining on a real 1.6M-event SAP purchase-to-pay log, plus a citation-grounding eval for LLM-written case narratives: every claim checked against the actual event log, not judged by a second model. Haiku 4.5 matches Sonnet 5 on grounding (100% of 186 citations) at under a third of the cost — the eval's real finding was which model to default to, not whether either hallucinated.
`Python` · `DuckDB` · `Claude API` · `matplotlib`

### Stack
`Python` · `RAG / retrieval` · `LLM evaluation` · `Claude API` · `DuckDB` · `ChromaDB` · `Streamlit` · `pytest` · `GitHub Actions`

### Background
MSc Financial Economics, Erasmus University Rotterdam. Previously KPMG.

[Portfolio](https://morichtereur.github.io/) · [LinkedIn](https://www.linkedin.com/in/moritz-richter-28297119a/)
