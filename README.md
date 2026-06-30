# AI Wordle Solver

An interactive Wordle solver and benchmarking environment for comparing heuristic search strategies. Built as a single Jupyter notebook with a Gradio front end, it lets you play against five AI opponents of increasing sophistication and measure their performance head-to-head.

## Overview

The project uses Wordle as a sandbox for practical AI search techniques — constraint propagation, candidate filtering, frequency heuristics, and entropy-based information gain — and provides a benchmarking framework to evaluate each strategy quantitatively rather than just anecdotally.
images/index.png

## Features

- Interactive Wordle game (Gradio interface)
- Five AI solvers of increasing sophistication
- Player vs. AI and AI vs. AI game modes
- Benchmarking framework across hundreds of randomized games
- Self-contained in a single notebook for easy experimentation

## AI Strategies

| # | Strategy | Approach | Concepts |
|---|----------|----------|----------|
| 1 | Random Guess | Picks any valid word, ignoring all prior feedback | Baseline |
| 2 | Random Candidate | Picks randomly among words consistent with prior feedback | Constraint propagation, candidate filtering |
| 3 | Positional Frequency | Scores candidates by per-position letter frequency | Positional frequency, greedy heuristic |
| 4 | Set Frequency | Scores candidates by frequency of unique letters across remaining candidates | Letter frequency heuristics |
| 5 | Entropy-Based | Selects the guess with highest expected information gain | Shannon entropy, information gain, adaptive search |

## Benchmarking

The notebook includes a benchmarking harness that runs each strategy over hundreds of randomly generated games and reports:

- Average guesses to solve
- Success rate
- Average runtime per game

This provides a direct, repeatable comparison between strategies rather than relying on a handful of manual trials.

## Tech Stack

- Python
- Gradio
- Pandas
- Jupyter Notebook

## Project Structure

```
AI-Wordle-Solver/
├── AI_Wordle_Solver.ipynb
├── README.md
├── requirements.txt
├── images/
└── datasets/        (future)
```

## Getting Started

```bash
git clone https://github.com/<palsoniii>/AI-Wordle-Solver.git
cd AI-Wordle-Solver
pip install -r requirements.txt
jupyter notebook
```

Open `AI_Wordle_Solver.ipynb` and run all cells. The Gradio interface will launch locally in your browser.

## Limitations

- The word bank is a placeholder set, not the official Wordle answer/guess lists.
- Entropy calculations are heuristic approximations, not exact minimax search.
- Benchmarks reflect performance against the current word bank only; results will shift once the official dataset is integrated.

## Roadmap

- Swap in the official Wordle answer and guess datasets
- Add benchmark visualizations (charts, distributions)
- Expand evaluation metrics (e.g., worst-case guesses, hard-mode performance)
- Support custom/user-supplied word lists

