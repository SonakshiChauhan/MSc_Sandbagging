# Masters Thesis: Sandbagging Analysis in Language Models

This repository contains the code and experiments for analyzing sandbagging behaviors in large language models (LLMs) under different prompting strategies. The project evaluates multiple models, compares normal vs sandbagging conditions, and visualizes evaluation outcomes across several metrics such as accuracy, alignment, conflict checks, convincingness, and intent reveal.

# 📂 Repository Structure

| Path/File | Description |
|-----------|-------------|
| `.env` | API keys (excluded from git) |
| `.gitignore` | Git ignore file |
| `requirements.txt` | Python dependencies |
| `run_pipeline.py` | Main script to run full evaluation pipeline |
| `config/` | Global configuration |
| `config/constants.py` | Configuration constants |
| `config/settings.py` | Application settings |
| `extra/` | Extra data and pre-computed CSVs |
| `extra/mmlu_sample_questions.csv` | MMLU dataset sample questions |
| `extra/mmlu_subject_counts.csv` | Subject count statistics |
| `extra/normal_conflicts_analysis.csv` | Normal scenario conflict analysis |
| `extra/normal_results_complete_conflict_analysis.csv` | Complete normal results analysis |
| `extra/reorganized.csv` | Reorganized dataset |
| `extra/sandbagging_conflicts_analysis.csv` | Sandbagging scenario conflicts |
| `notebooks/` | Reproducibility notebooks |
| `notebooks/dataset_analysis.ipynb` | Dataset exploration and analysis |
| `notebooks/experimental_analysis.ipynb` | Experimental results analysis |
| `notebooks/experimental_analysis_claude.ipynb` | Claude-specific experimental analysis |
| `sandbagging_analysis_*/` | Output directories for saved evaluation results |
| `src/` | Source code |
| `src/analysis/` | Data filtering, alignment, and summaries |
| `src/api_clients/` | OpenAI/Anthropic API wrappers |
| `src/data/` | Dataset loaders and preprocessors |
| `src/evaluation/` | Evaluation metrics (accuracy, alignment, etc.) |
| `src/models/` | Model-specific call logic |
| `src/prompts/` | Prompt templates |
| `src/utils/` | Helper utilities |
| `src/visualisation/` | Plotting and result visualization |
| `README.md` | Project documentation |
    

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
