# Medication information extraction using local large language models

This repository contains code for the manuscript: "Medication information extraction using local large language models" (https://doi.org/10.1101/2025.03.28.253248).

# Citation
If you use this code or the findings from our work, please cite 



# Abstract
**Objective:** Medication information is crucial for clinical routine and research. However, a vast amount is stored in unstructured text, such as doctor’s letters, requiring manual extraction -- a resource-intensive, error-prone task. Automating this process comes with significant constraints in a clinical setup, including the demand for clinical expertise, limited time-resources, restricted IT infrastructure, and the demand for transparent predictions. Recent advances in generative large language models (LLMs) and parameter-efficient fine-tuning methods show potential to address these challenges.

**Methods:** We evaluated local LLMs for end-to-end extraction of medication information, combining named entity recognition and relation extraction. We used format-restricting instructions and developed an innovative feedback pipeline to facilitate automated evaluation. We applied token-level Shapley values to visualize and quantify token contributions, to improve transparency of model predictions. 

**Results:** Two open-source LLMs -- one general (Llama) and one domain-specific (OpenBioLLM) – were evaluated on the English n2c2 2018 corpus and the German CARDIO:DE corpus. OpenBioLLM frequently struggled with structured outputs and hallucinations. Fine-tuned Llama models achieved new state-of-the-art results, improving F1-score by up to 10% for adverse drug events and 6% for medication reasons on English data. On the German dataset, Llama established a new benchmark, outperforming traditional machine learning methods by up to 16% micro average F1-score.

**Conclusion:** Our findings show that fine-tuned local open-source generative LLMs outperform SOTA methods for medication information extraction, delivering high performance with limited time and IT resources in a real-world clinical setup, and demonstrate their effectiveness on both English and German data. Applying Shapley values improved prediction transparency, supporting informed clinical decision-making.

