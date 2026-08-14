# People Analytics — Predicting Attrition & Job-Change Risk

A small machine learning project that predicts two things using real HR data:
1. **Which employees are likely to leave a company** (attrition)
2. **Which job candidates are likely to keep job-hunting** after training (job change)

## What's in this project

```
data/                        The two datasets (CSV files)
analysis.ipynb                The main notebook — run this. Loads the data, trains
                               both models, and shows all results, charts, and tables.
results/                      Output from the notebook: metrics, saved models, charts
requirements.txt              Python packages needed to run the notebook
```

## How to run it

You need Python with Jupyter installed. Two easy ways:

**Using conda:**
```bash
conda activate base
jupyter notebook
```
Then open `analysis.ipynb` in the browser tab that opens, and run
**Kernel → Restart & Run All**.

**Using a virtual environment:**
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook analysis.ipynb
```

That's it — the notebook does everything: loads the data, trains the models, prints
the results, and draws all the charts, right there in the browser.

## What the models found

| Model | Predicts | How good is it? |
|---|---|---|
| Random Forest | Will an employee leave? | Catches about 6 in 10 people who actually leave |
| LightGBM | Is a candidate still job-hunting? | Catches about 7 in 10 people who are |

Both models are far better than guessing. The main things driving each prediction:
- **Employees leave** mostly over **pay, career stage, and workload**
- **Candidates keep job-hunting** mostly based on **training engagement and their local job market**
