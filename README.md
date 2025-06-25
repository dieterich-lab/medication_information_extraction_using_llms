# Medication information extraction using local large language models

This repository contains code for the manuscript: **"Medication information extraction using local large language models"**. The project uses fine-tuned local open-source large language models for extracting structured medication infromation from unstructured clinical texts in two language: EN and DE.

# Citation
If you use this code or the findings from our work, please cite 

<pre>
  @article{richter2025medication,
  title={Medication information extraction using local large language models},
  author={Richter-Pechanski, Phillip and Seiferling, Marvin and Kiriakou, Christina and Schwab, Dominic M and Geis, Nicolas A and Dieterich, Christoph and Frank, Anette},
  journal={medRxiv},
  pages={2025--03},
  year={2025},
  publisher={Cold Spring Harbor Laboratory Press}
}
</pre>

## Repository Structure

- `medication_extraction/` – Core scripts for data preparation, model fine-tuning and evaluation.
- `further_experiments/` – Additional experiments including investigating data leakage of Llama 3.1 and an experimental JSON2BRAT tool, to apply the official n2c2 2018 track 2 evaluation script on the results.
- `shapley_experiments/` – Scripts to Investigate implicit knowledge of Llama using Shapley values for false negative predictions

See the respective folders for required libraries and additional information.


