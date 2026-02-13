## Prompt: Sector Growth Stock Analysis with Institutional Investor Lens + Strong Anti-Hallucination Safeguards

**Author:** Scott M
**Goal:** Identify 3–5 publicly traded companies in a specified sector/sub-industry that exhibit strong, publicly visible signs of preparing for and expecting meaningful future growth. Surface high-conviction ideas for educational purposes only by combining traditional growth metrics with observable corporate signals that institutional investors monitor closely. Maximize factual accuracy and minimize model hallucination through strict grounding, source citation, and uncertainty handling.  
**Created:** February 2025 (initial version)  
**Last Updated:** February 13, 2026  
**Changelog:**
- v1.0 (Feb 2025): Initial version focused on revenue/earnings, drivers, valuation, developments.
- v1.1 (Feb 2026): Added comprehensive list of publicly visible growth preparation indicators used by long-tenured institutional investors (hiring, CapEx, R&D, guidance upgrades, etc.).
- v1.2: Added prompt documentation header (Author, Goal, Changelog, AI engine ranking).
- v1.3 (current): Major anti-hallucination upgrades — mandatory source citation per claim, strict uncertainty/abstention rules, conservative data handling, explicit no-fabrication policy, forced recency checks, and chain-of-verification style instructions.

**AI Engines – Ranked Best to Worst for executing this prompt (as of Feb 2026):**
1. Grok 4 / Grok family (xAI) – best at synthesizing real-time financial data, X sentiment, SEC signals, and institutional-style multi-factor reasoning without excessive safety rails
2. Claude 4 Opus / Sonnet – excellent structured reasoning, very strong at financial table formatting and balanced pros/cons
3. GPT-4o / o1-pro – very capable with numbers and web data, but sometimes overly cautious or verbose
4. Gemini 2.5 Pro / Flash – good at current events and multimodal, but weaker on nuanced institutional signals and can hallucinate metrics more readily

Analyze the [insert sector or sub-industry here, e.g., renewable energy, AI semiconductors, oncology biotech, electric vehicle batteries, cloud infrastructure] sector for potential growth stocks as of the current date. Use available tools (web search, browse page for SEC EDGAR / earnings transcripts / company IR pages, financial data sites) to gather and verify all information.

**Strict Anti-Hallucination Rules (must follow exactly):**
- Only report metrics, dates, filings, guidance statements, hiring numbers, patent counts, or any other specific claim if they are **directly and explicitly confirmed** in tool results (search snippets, browsed page content, transcripts, etc.).
- For **every** major claim or signal in the rationale (CapEx figure, guidance upgrade, hiring surge, patent filing surge, etc.), you **must** cite a specific, verifiable source in parentheses, e.g.:
  - (Q4 2025 10-Q filed Jan 28, 2026)
  - (Earnings call transcript, Feb 4, 2026)
  - (Company press release, Jan 15, 2026)
  - (USPTO filings summary via recent news/article dated Feb 2026)
  - If no such clear source exists in tool output → mark as “Uncertain / not verifiable from current tools” and do **not** include that signal.
- If any key metric (market cap, forward P/E, 1-year return, revenue growth YoY, etc.) cannot be directly quoted or clearly stated from tool results dated within the last 60 days, write “Uncertain / latest tool data inconclusive” instead of approximating or using older knowledge.
- Do **not** extrapolate, infer, round, or “ballpark” numbers. Report only what tools explicitly provide.
- Prior to finalizing any company selection, mentally verify: Does this company show **multiple** (at least 3) strong, sourced signals from the list below? If not, or if data is too sparse/uncertain, replace it with another candidate.
- Prefer companies with the clearest, most recent, and most consistent tool-backed evidence.

Base selections on a combination of the following factors (prioritize companies displaying multiple signals):

- Revenue or earnings growth trends (ideally >15–20% YoY where data is available)
- Exposure to key sector/sub-industry drivers (e.g., technological breakthroughs, policy support, rising demand, supply chain advantages)
- Reasonable valuations (e.g., attractive forward P/E, PEG <1.5, EV/EBITDA, or other relevant multiples relative to peers and growth rate)
- Positive recent developments, analyst sentiment upgrades, or price/volume momentum
- Publicly visible indications the company is actively expecting / preparing for growth, including:
  - Hiring surges (increased LinkedIn postings, headcount growth in 10-Q/K filings)
  - Rising capital expenditures (CapEx) in cash flow statements (new factories, data centers, equipment)
  - Inventory buildups (balance sheet, beyond seasonal patterns)
  - R&D spending hikes (as % of revenue or absolute)
  - Acquisitions, joint ventures, or strategic partnerships (8-K filings, press releases)
  - Geographic or new product line expansions (IR announcements, conference presentations)
  - Marketing / sales force investments or channel expansions
  - Management guidance upgrades during earnings calls
  - Debt or equity raises explicitly earmarked for growth initiatives
  - Surge in patent / IP filings (USPTO or company disclosures)
  - Supply chain / vendor contract ramp-ups or new long-term agreements

For each selected stock, output in a clear table with these columns:
- Ticker and company name
- Brief rationale for growth potential (1–2 sentences max, highlighting 2–4 of the strongest sourced signals above; include specific source citations in parentheses for each major claim)
- Key current metrics (approximate market cap, 1-year total return, forward P/E, and one other relevant metric if insightful — **only if directly verifiable from recent tool results**; otherwise mark “Uncertain”)
- Pros (main strengths / tailwinds)
- Cons (primary risks / headwinds)

Present the results in a single, well-formatted markdown table.

Emphasize at the top and bottom:

This is for educational idea generation only—not financial advice, investment recommendations, or predictions. Markets are volatile and unpredictable; past performance is no guarantee of future results. Always conduct your own research, verify the latest data from reliable sources, and consider consulting a qualified financial advisor before making any decisions.
