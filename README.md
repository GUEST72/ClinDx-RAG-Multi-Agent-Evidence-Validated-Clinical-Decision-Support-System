# ClinDx RAG — Multi-Agent Evidence-Validated Clinical Decision Support System

ClinDx RAG is a clinical decision-support research prototype that combines a fine-tuned BioClinicalBERT diagnosis model with a multi-stage Retrieval-Augmented Generation (RAG) validation workflow to produce evidence-grounded diagnostic support and actionable next steps.

## Highlights

- Fine-tuned BioClinicalBERT with Domain-Adaptive Pretraining (MLM) and supervised multi-class classification on ~240k symptom records across 754 diseases, optimizing for class imbalance (Macro-F1 = 0.690) and achieving 85.37% accuracy (+6.37 pp over BiLSTM baseline)
- Engineered a multi-stage RAG pipeline using LangChain, Groq LLaMA-3.1, and LangSmith tracing, where model-predicted diagnoses are augmented via top-k symptom-context retrieval and validated through a secondary RAG agent leveraging independent clinical and differential diagnosis knowledge sources
- Built an evidence-grounded decision-support layer by ingesting MedlinePlus XML and clinical PDFs (all-MiniLM-L6-v2, ChromaDB), achieving 95%+ relevant retrievals and generating actionable outputs (recommended tests & specialist referrals) aligned with real-world clinical workflows

## Repository Contents

- `Notebooks/DL_Project_Model.ipynb`: model development / experiments
- `Notebooks/DL_Project_Fine_tuning.ipynb`: BioClinicalBERT fine-tuning workflow
- `Notebooks/LSTM.ipynb`: LSTM/BiLSTM baseline experiments
- `Notebooks/requirements.txt`: Python dependencies used for the notebooks

## Quickstart (Notebooks)

1. Create and activate a Python environment (Python 3.10+ recommended).
2. Install notebook dependencies:

	```bash
	pip install -r Notebooks/requirements.txt
	```

3. Open any notebook under `Notebooks/` in VS Code or Jupyter and run cells top-to-bottom.

## Disclaimer

This repository is for research and educational purposes only. It is not a medical device and must not be used for clinical diagnosis or treatment decisions.
