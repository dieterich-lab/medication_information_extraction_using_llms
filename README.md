# Medication Information Extraction Using Local Large Language Models

Code for the paper **“Medication Information Extraction Using Local Large Language Models”** (Journal of Biomedical Informatics, 2025).

This repository contains notebooks and scripts for **end-to-end medication information extraction** from clinical text using **local open-source LLMs**. The work covers **English** and **German** clinical data and combines:

- data preparation
- supervised fine-tuning of local LLMs
- structured JSON inference
- relation-level evaluation
- follow-up analyses for feedback-based error inspection and Shapley-value interpretability

The project focuses on extracting structured medication information such as **medication**, **ADE**, **strength**, **frequency**, **duration**, **route**, **form**, **dosage**, and **reason**.

## Repository layout

```text
.
├── medication_extraction/
│   ├── brat2json.ipynb
│   ├── train_llm.ipynb
│   ├── inference_llm.ipynb
│   ├── evaluate_llm.ipynb
│   └── requirements.txt
├── further_experiments/
│   ├── data_leakage.ipynb
│   ├── feedback_LLM.ipynb
│   ├── json2brat.ipynb
│   ├── evaluate_n2c22018.py
│   ├── requirements_fe.txt
│   └── oac_shift_analysis.ipynb
├── shapley_experiments/
│   ├── investigate_implicit_knowledge_ade.ipynb
│   └── requirements_shap.txt
└── README.md
```

## What each folder contains

### `medication_extraction/`
Main pipeline for the paper:

- **`brat2json.ipynb`**: converts annotated data into the project’s JSON / pickle format
- **`train_llm.ipynb`**: fine-tunes a local **Meta-Llama-3.1-8B** model for structured medication extraction
- **`inference_llm.ipynb`**: runs batched inference and writes predictions to a pipe-delimited CSV
- **`evaluate_llm.ipynb`**: computes exact and lenient precision / recall / F1, including confidence intervals

### `further_experiments/`
Additional analyses reported in the paper appendix:

- **`data_leakage.ipynb`**: checks potential memorization / leakage effects
- **`feedback_LLM.ipynb`**: investigates semantically correct false predictions using a feedback pipeline
- **`json2brat.ipynb`**: converts project JSON back to BRAT-style output
- **`evaluate_n2c22018.py`**: n2c2 evaluation script used for comparison
- ""`oac_shift_analysis.ipynb`"": detecting anticoagulation shift in 2012 and 2021 medical text corpora

### `shapley_experiments/`
Interpretability experiments:

- **`investigate_implicit_knowledge_ade.ipynb`**: uses token-level Shapley values to analyze implicit ADE knowledge and false negatives

## Setup

The notebooks in this repository were prepared for **Python 3.11.2** on a **Linux-compatible** system.

```bash
python3.11 -m pip install virtualenv
virtualenv venv --python=python3.11
source venv/bin/activate
```

Install dependencies for the part of the repo you want to run:

```bash
# Main experiments
pip install -r medication_extraction/requirements.txt

# Additional appendix experiments
pip install -r further_experiments/requirements_fe.txt

# Shapley experiments
pip install -r shapley_experiments/requirements_shap.txt
```

To use the notebooks in Jupyter:

```bash
pip install ipykernel jupyter
python -m ipykernel install --user --name medication-llm --display-name "Python (medication-llm)"
jupyter notebook
```

## Minimal workflow

1. **Prepare annotations** with `medication_extraction/brat2json.ipynb`
2. **Fine-tune** the model with `medication_extraction/train_llm.ipynb`
3. **Run inference** with `medication_extraction/inference_llm.ipynb`
4. **Evaluate outputs** with `medication_extraction/evaluate_llm.ipynb`
5. Optionally run **feedback** and **Shapley** analyses from the other folders

## Data sources

The paper evaluates local LLMs on:

- **2018 n2c2 Track 2** (English medication / ADE extraction)
- **CARDIO:DE** (German clinical corpus)

Please obtain these datasets from their original sources and comply with their respective licenses, terms of use, and access requirements.

## Notes

- Fine-tuning and inference are set up for local model execution and assume access to suitable compute, typically a CUDA-capable GPU.
- Paths, model names, and output filenames are configured directly in the notebooks and may need to be adapted to your environment.

## Citation

If you use this repository, please cite the paper:

```bibtex
@article{richter_pechanski_2025_medication,
  author  = {Richter-Pechanski, Phillip and Seiferling, Marvin and Kiriakou, Christina and Schwab, Dominic M. and Geis, Nicolas A. and Dieterich, Christoph and Frank, Anette},
  title   = {Medication Information Extraction Using Local Large Language Models},
  journal = {Journal of Biomedical Informatics},
  volume  = {169},
  pages   = {104898},
  year    = {2025},
  doi     = {10.1016/j.jbi.2025.104898}
}
```

## License

This repository is released under the **MIT License**. See `LICENSE` for details.
