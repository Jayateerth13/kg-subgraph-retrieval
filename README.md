# Efficient Subgraph Retrieval for Knowledge Graph-Enhanced LLMs

CS 255 project — Venkat Anoop Karlapudi & Jayateerth Kamatgi

Main artifact: `notebooks/kg_subgraph_retrieval.ipynb` (MetaQA KG loading + several subgraph retrieval methods + evaluation/plots).

TransE-based retrieval: `notebooks/trans-E-v1.ipynb` and `notebooks/trans-E-v2.ipynb`. These improve on the 4 baselines.

## Setup

```bash
cd /path/to/kg-subgraph-retrieval
python3 -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

## Data

Place MetaQA under `data/raw/`:

```
data/raw/
├── kb.txt
├── 1-hop/vanilla/qa_train.txt, qa_dev.txt, qa_test.txt
├── 2-hop/vanilla/qa_train.txt, qa_dev.txt, qa_test.txt
└── 3-hop/vanilla/qa_train.txt, qa_dev.txt, qa_test.txt
```

## Run

Start Jupyter from `notebooks/`:

```bash
source venv/bin/activate
cd notebooks
jupyter notebook kg_subgraph_retrieval.ipynb
# or: jupyter lab kg_subgraph_retrieval.ipynb
```

Run cells top to bottom. The evaluation section writes `results_summary.json` at the repo root.

## Colab

Only the TransE notebooks (`notebooks/trans-E-v1.ipynb`, `notebooks/trans-E-v2.ipynb`) are intended to be run in Google Colab. For Colab runs, make sure `datasets.zip` is present and extracted so the notebook can find the dataset files.

## Optional: Groq LLM cells

If you want to run the Groq API cells, create `notebooks/.env`:

```
GROQ_API_KEY=your_key_here
```

## Project structure

```
notebooks/
└── kg_subgraph_retrieval.ipynb   # main pipeline + evaluation
data/
├── raw/                          # MetaQA KB + QA splits
results_summary.json             # written by the notebook (after eval cell)
requirements.txt
```
