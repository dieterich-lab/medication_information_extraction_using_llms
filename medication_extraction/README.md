# MEdication information extraction

This repository contains code for the main experiments for medication information extraction: data pre-processing, model fine-tuning, model inference and model evaluation.
## Contents

- `brat2json.ipynb`  
  Our custom data pre-processing tool. It converts n2c2 BRAT-formated data into our custom JSON format and saves tje resulting dataset as pickle files.

- `train_llm.ipynb`  
  Fine-tuning a Llama 3.1 model on n2c2 2018 training split.

- `inference_llm.py`  
  Usng the fine-tuned Llama 3.1 to do inference on the n2c2 2018 test split.

- `evaluate_llm.py`  
  Calculating precision, recall and f1-score per relation information class and printing a classification report for lenient and exact matching.

- `requirements.txt`  
  List of dependencies required to run the above experiments.

## Setup



1. Create and activate a virtual environment on a Linux-compatible machine using Python 3.11.2
```bash
python3.11 -m pip install virtualenv
virtualenv venv --python=python3.11
source venv/bin/activate      
```

2. Install required dependencies
```bash
pip install -r requirements.txt
```

3. Add the venv to Jupyter
```bash
pip install ipykernel
python -m ipykernel install --user --name=shapley --display-name "Python (shapley)"
```

4. Open Jupyter and select the shapley kernel
```bash
jupyter notebook
```




