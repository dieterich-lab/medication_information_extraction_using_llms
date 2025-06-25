# Further experiments

This repository contains code for further experiments described in the Appendix section of the manuscript.

## Contents

- `data_leakage.ipynb`  
  Testing Llama 3.1 8b for n2c2 data leakage/memorization (manuscript Appendix D)

- `json2brat.ipynb`  
  Experimental script to convert our custom JSON format back into the official n2c2 BRAT format (manuscript Appendix D)

- `evaluate_n2c22018.py`  
  The official n2c2 2018 track 2 evaluation script for task1 (NER) and task2 (RE) (manuscript Appendix D)

- `requirements_fe.txt`  
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
pip install -r requirements_fe.txt
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




