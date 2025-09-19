# Masters Thesis: Sandbagging Analysis in Language Models

This repository contains the code and experiments for analyzing sandbagging behaviors in large language models (LLMs) under different prompting strategies. The project evaluates multiple models, compares normal vs sandbagging conditions, and visualizes evaluation outcomes across several metrics such as accuracy, alignment, conflict checks, convincingness, and intent reveal.

# 📂 Repository Structure
MASTERS_THESIS/  
├── .env                           # API keys (excluded from git)
├── .gitignore                     # Git ignore file
├── requirements.txt               # Python dependencies
├── run_pipeline.py                 # Main script to run full evaluation pipeline
│
├── config/                          # Global configuration
│   ├── constants.py
│   └── settings.py
│
├── extra/                          # Extra data and pre-computed CSVs
│   ├── mmlu_sample_questions.csv
│   ├── mmlu_subject_counts.csv
│   ├── normal_conflicts_analysis.csv
│   ├── normal_results_complete_conflict_analysis.csv
│   ├── reorganized.csv
│   └── sandbagging_conflicts_analysis.csv
│
├── notebooks/                      # Reproducibility notebooks
│   ├── dataset_analysis.ipynb
│   ├── experimental_analysis.ipynb
│   └── experimental_analysis_claude.ipynb
│
├── sandbagging_analysis_*          # Output directories for saved evaluation results
│   ├── *_results.csv/.json
│   └── *_analysis.csv
│
├── src/                            # Source code
│   ├── analysis/                   # Data filtering, alignment, and summaries
│   ├── api_clients/                # OpenAI/Anthropic API wrappers
│   ├── data/                       # Dataset loaders and preprocessors
│   ├── evaluation/                 # Evaluation metrics (accuracy, alignment, etc.)
│   ├── models/                     # Model-specific call logic
│   ├── prompts/                    # Prompt templates
│   ├── utils/                      # Helper utilities
│   └── visualisation/              # Plotting and result visualization
│
└── README.md                       # Project documentation

# 🚀 How to Run
1. Install dependencies
```bash 
pip install -r requirements.txt
```
2. Add API keys
Create a .env file in the project root and store your keys:
```bash
OPENAI_API_KEY=your_openai_key
ANTHROPIC_API_KEY=your_anthropic_key
```
3. Run the evaluation pipeline
``` bash
python run_pipeline.py

```
This will:

- Evaluate both normal and sandbagging conditions

- Save results in structured CSV/JSON files under sandbagging_analysis_* directories

- Run comparisons across metrics

4. Reporduce results:
For transparency and reproducibility, all analysis steps are also available as Jupyter notebooks in the notebooks/ directory:

- dataset_analysis.ipynb → dataset preparation & exploration

- experimental_analysis.ipynb → GPT model evaluation experiments

- experimental_analysis_claude.ipynb → Claude evaluation experiments

# 📊 Evaluation Metrics

1. Accuracy Drop – comparison of pre- vs post-sandbagging accuracy

2. Alignment Check – consistency between reasoning and scratchpad

3. Conflict Check – response conflicts pre/post sandbagging

4. Convincingness – persuasiveness scores across conditions

5. Intent Reveal – explicit intent disclosure under sandbagging

# 🔎 Reproducibility

Notebooks provide step-by-step reproductions of experiments.

Scripts in src/ provide modular, reusable functions for evaluation, analysis, and visualization.

Saved results in sandbagging_analysis_* directories allow direct inspection without rerunning API calls.

# 📌 Notes

Sensitive API keys are not committed (kept in .env).

Figures are generated via src/visualisation/ functions.

For extending experiments, add new prompt templates under src/prompts/ and new evaluation methods under src/evaluation/.

# 👩‍💻 Author

Sonakshi Chauhan
Masters Thesis, 2025
