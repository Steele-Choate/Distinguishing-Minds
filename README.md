# Evolving Distinguishing Minds

## Project Overview

Evolving Distinguishing Minds is a Python-based multiplayer text adventure and experimental human-AI identity judgment system. The project places the player in a simulated research facility where different drone characters may be controlled by humans, baseline AI agents, or multi-agent AI systems.

The goal of the project is to evaluate whether a structured multi-agent reasoning pipeline can improve human-AI identity classification compared to a single-prompt baseline model. The system compares baseline and agentic AI behavior using metrics such as classification accuracy, deception success rate, estimated token usage, and response latency.

## Features

- Text-based exploration game with a Tkinter graphical interface
- Room-based map navigation
- Inventory system with item tooltips
- Puzzle-solving mechanics
- Human, baseline AI, and multi-agent AI drone roles
- Human-vs-AI identity judgment system
- Baseline single-prompt AI response generation
- Multi-agent pipeline with persona, context, critic, and decision stages
- Optional LangGraph support for the agentic workflow
- Ollama backend support using `llama3:8b`
- Local GPT-2 fallback through Hugging Face Transformers
- Logging of experiment results to JSON and CSV files
- Plot generation for performance, latency, token usage, and deception metrics
- Optional multiplayer socket support

## Project Structure

```text
project-folder/
│
├── main.py
├── requirements.txt
├── README.md
│
├── rooms/
│   └── room image files
│
├── items/
│   └── item image files
│
├── strategy_memory/
│   └── saved agent strategy memory files
│
├── human_response_bank.json
├── human_prompt_bank.json
├── agentic_eval_log.json
├── identity_experiment_log.json
└── generated plot/image output files
````

Note: Some JSON log files and generated plot files are created automatically when the program runs.

## Installation

This project requires Python 3.10 or newer.

First, create a virtual environment:

```bash
python -m venv venv
```

Activate the virtual environment.

On Windows:

```bash
venv\Scripts\activate
```

On macOS/Linux:

```bash
source venv/bin/activate
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

## Ollama Setup

The standard and hard difficulty modes use Ollama with the `llama3:8b` model.

Install Ollama from:

```text
https://ollama.com/
```

Then pull the required model:

```bash
ollama pull llama3:8b
```

Make sure Ollama is running before launching the game.

## Running the Program

Run the main Python file:

```bash
python main.py
```

If your main file has a different name, replace `main.py` with the correct filename.

## Difficulty Modes

The project includes different model modes:

* Easy: uses a local Hugging Face GPT-2 text generation pipeline
* Standard: uses Ollama with `llama3:8b`
* Hard: uses Ollama with `llama3:8b`

## Output Files

The program may generate several output files, including:

* `agentic_eval_log.json`
* `agentic_eval_summary.json`
* `agentic_eval_log.csv`
* `identity_experiment_log.json`
* `identity_experiment_summary.json`
* `identity_experiment_log.csv`
* `baseline_vs_agentic_performance.png`
* `baseline_vs_agentic_cost.png`
* `baseline_vs_agentic_progress.png`
* `human_judgment_accuracy.png`
* `trial_accuracy_progress.png`
* `trial_deception_progress.png`
* `trial_token_usage_progress.png`
* `trial_latency_progress.png`
* `trial_all_metrics_bar.png`

These files store experiment logs, summaries, and visualizations used to evaluate baseline and multi-agent AI performance.

## Notes

* Tkinter is included with most standard Python installations, but some Linux distributions may require installing it separately.
* The `rooms` and `items` folders should contain the image assets used by the game.
* The program can still create required directories automatically if they do not already exist.
* LangGraph is optional in the code. If it is installed, the multi-agent pipeline can run as a compiled graph. If it is unavailable, the program falls back to sequential execution.
* Ollama must be installed separately because it is not a normal Python package.

## Research Purpose

This project supports the research paper:

"Evolving Distinguishing Minds: A Multi-Agent Framework for Human-AI Identity Judgment in Multiplayer Text-Based Games"

The system is designed to test whether multi-agent reasoning improves identity classification and conversational consistency while measuring the trade-offs in computational cost, latency, and human-likeness.
