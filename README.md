# Task_05_Descriptive_Stats
# Task_05_Descriptive_Stats

## Overview
This repository documents Research Task 05, focused on evaluating how effectively large language models (LLMs) such as ChatGPT, Claude, or GitHub Copilot can interpret and reason about structured sports datasets.

The goal is to simulate real-world coaching and performance analysis questions using a small public dataset — specifically, the Syracuse Women’s Lacrosse 2025 season. Using a combination of descriptive statistics, visualization, and prompt engineering, we evaluate both the capabilities and limitations of modern LLMs.

---

## Repository Contents

| Folder/File     | Description |
|------------------|-------------|
| `scripts/`       | Jupyter notebooks and Python scripts for computing and visualizing statistics from the dataset |
| `prompts/`       | Natural language prompts used to interact with LLMs |
| `README.md`      | This documentation file explaining the task, structure, and how to use the repository |

---

## How to Use This Repo

1. Dataset Access  
   Download your dataset externally (e.g., from https://cuse.com/sports/2013/1/16/WLAX_0116134638) — do **not** include it in the GitHub repository.

2. Statistics Generation  
   Run the notebook in `scripts/descriptive_stats_validation.ipynb` to generate key performance metrics (e.g., game count, average goal margins).

3. Prompt & Interact with LLMs  
   Use the files in the `prompts/` folder to query your preferred LLM (e.g., ChatGPT). These include questions of increasing complexity, such as:
   - "How many games did this team play?"
   - "Who was the most improved player?"
   - "Should the coach focus on offense or defense next season?"

4. LLM Response Validation  
   Manually or programmatically validate the responses using your computed stats. Record which prompts yielded accurate or misleading results, and why.

---

## Research Focus

This task is not just about producing correct answers, but about:
- Exploring how LLMs understand structured datasets
- Identifying where they succeed or fail
- Designing prompts that guide the model toward accurate reasoning
- Understanding LLM hallucinations, bias, or confusion

Failures, incorrect answers, and creative prompt engineering are all part of the research output and should be documented.

---

## Submission Instructions

- Do NOT include the dataset in your GitHub repository.
- Email your public GitHub repo link to: `jrstrome@syr.edu`
- Report your research activity via the following Qualtrics link:
  - https://syracuseuniversity.qualtrics.com/jfe/form/SV_cDgnzM695AMx8d8
  - Reports are due by July 31 and August 15

---

## Research Workflow Summary

### Dataset Used
- Source: Syracuse Women’s Lacrosse 2025 season
- Fields Included: Date, Opponent, Result, GoalsFor, GoalsAgainst

### Analysis Performed (`descriptive_stats_validation.ipynb`)
- Loaded and parsed game-level data.
- Computed number of games played: 18
- Calculated average goal margin: +3.4
- Generated goal difference time-series visualization.
- Defined `GoalDiff` as a metric to evaluate team performance trends across the season.

### LLM Interaction

#### Model Used
- Model: ChatGPT (gpt-4o)
- Interface: ChatGPT Web

#### Prompts Tested
1. "How many games did the Syracuse Women’s Lacrosse team play this season?"  
   - LLM correctly responded with 18 games using the provided data.

2. "Which player showed the greatest improvement in goal-scoring from the first half of the season to the second half?"  
   - LLM required clarification on how to define "improvement". When supplied with a metric (e.g., goals in last 5 vs. first 5 games), it identified top scorers but hallucinated player names not in dataset.

3. "As a coach, should I focus on offense or defense to win 2 more games next season?"  
   - LLM made a plausible argument for strengthening defense due to two close losses but failed to attribute reasoning to actual game results.

### Insights
- LLMs can process and summarize basic numerical patterns accurately if data is explicitly embedded in context.
- Complex evaluative prompts (e.g., coaching decisions or player improvement) require tight definition of metrics and guidance.
- LLMs may hallucinate or overgeneralize in the absence of structured player-level statistics.

---
