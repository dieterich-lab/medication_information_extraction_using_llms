# Interpretability Experiments using Shapley values

This folder contains experiments designed to investigate implicit knowledge of Llama models using Shapley values for false negative predictions. See manuscript Appendix C.

## Contents

- `investigate_implicit_knowledge_ade.ipynb`  
  Investigate implicit ADE knowledge of LLMs using Shapley values. The script calculates Shapley values for ADE FN conducts significance tests on the results.

- `requirements_shap.txt`  
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
pip install -r requirements_shap.txt
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


