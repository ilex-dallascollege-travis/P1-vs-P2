# P1-vs-P2
This repo is desgined to compare ai trading robots, compiling hypothesis, continuing experiments, data sheets, ai agents to analyze data, and gather information from others research

# AI Trading Robot Comparative Analysis & Research Hub

This repository is designed to systematically compare AI trading robot prototypes (Prototype 1 vs. Prototype 2). It serves as a centralized workspace for compiling hypotheses, running ongoing experiments, storing performance data sheets, deploying AI analysis agents, and synthesizing external market research.

## Core Objectives

* **Head-to-Head Comparison:** Benchmark performance, risk metrics, and execution behavior between P1 and P2 under identical market conditions.
* **Hypothesis Tracking:** Document testable theories regarding strategy adjustments, signal weights (e.g., sentiment vs. technicals), and model architectures.
* **Continuous Experimentation:** Maintain reproducible logs, configuration files, and results for every iterative test run.
* **Automated Data Analysis:** Utilize AI agents to parse trade logs, detect anomalies, and generate performance summaries.
* **External Research Synthesis:** Aggregate and organize findings from academic papers, open-source projects, and quantitative trading literature.

## Repository Structure

## Repository Structure & Category Breakdown

### 1. `/data` — Trade Logs & Standardized Metrics
Stores all quantitative outputs from P1 and P2 test runs.
* **`/data/raw`**: Unprocessed trade logs, raw API outputs, and market data dumps (ignored by Git via `.gitignore` to keep the repo lightweight).
* **`/data/processed`**: Clean, standardized CSV sheets ready for AI agent analysis.
  * `_TEMPLATE_trades.csv`: Unified trade-by-trade log schema (`bot_id`, timestamps, prices, PnL, `signal_trigger`, and `market_regime`).
  * `_TEMPLATE_summary.csv`: High-level scorecard comparing P1 and P2 across net profit, win rate, profit factor, max drawdown, and Sharpe ratio.

### 2. `/experiments` — Iterative Test Runs
Isolated folders (`exp-001`, `exp-002`, etc.) documenting individual head-to-head runs.
* **`_TEMPLATE_README.md`**: Standard experiment log recording run dates, linked hypotheses, market regime, parameter differences, and high-level metric deltas.

### 3. `/hypotheses` — Scientific Theory Tracking
Tracks every proposed improvement before and after testing to prevent guesswork and overfitting.
* **`_TEMPLATE.md`**: Structured `If / Then / Because` hypothesis format defining independent variables, control constants, numerical success criteria, and final validation status (`Draft`, `Active`, `Validated`, `Invalidated`, or `Inconclusive`).

### 4. `/agents` — AI Analysis & Review Roster
Contains modular Markdown system prompts designed to be copied into web-based AI chats alongside your CSVs or code snippets.

| Agent File | Purpose & Role |
| :--- | :--- |
| **`data-analyst.md`** | Compares P1 vs. P2 trade logs, calculates performance gaps, spots behavioral divergences, and flags execution anomalies. |
| **`hypothesis-architect.md`** | Evaluates test results against pre-set success criteria, drafts conclusion blocks, and designs the next single-variable experiment. |
| **`research-synthesizer.md`** | Converts external articles, papers, and open-source strategies into structured `/research` notes and testable hypotheses. |
| **`signal-auditor.md`** | Ranks individual triggers (e.g., news sentiment, politician trades) by profitability, detects false positives, and suggests filtering rules. |
| **`risk-red-teamer.md`** | Stress-tests results by removing top outlier trades, checking losing streaks, testing regime fragility, and estimating real-world slippage. |
| **`code-logic-reviewer.md`** | Audits decision rules and code diffs between P1 and P2 for lookahead bias, missing-data edge cases, and curve-fitting. |

### 5. `/research` — External Knowledge Base
Curated notes and summaries from external quantitative finance papers, articles, and community findings.
* **`_TEMPLATE.md`**: Standard research note format capturing the core thesis, actionable takeaways for P1 and P2, and links to new hypotheses generated from the reading.


## Workflow & Methodology

1. **Formulate:** Copy `hypotheses/_TEMPLATE.md` to create a new hypothesis (`HYP-XXX.md`) before altering any bot parameters.
2. **Execute:** Run P1 and P2 side-by-side and record run settings in `experiments/exp-XXX/README.md`.
3. **Standardize:** Format trade logs and final metrics into `/data/processed` using the CSV templates.
4. **Analyze & Audit:** Run the processed CSVs through **`data-analyst.md`**, **`signal-auditor.md`**, and **`risk-red-teamer.md`**.
5. **Conclude & Iterate:** Use **`hypothesis-architect.md`** to score the hypothesis, update your files, and plan the next test cycle.
