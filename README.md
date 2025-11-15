# Pantry-Pal
## Project Overview
This project aims to develop a user-centric and practical cooking assistant for ingredient-based recipe generation and retrieval.
The dataset used is [Food.com Recipes with Search Terms and Tags](https://www.kaggle.com/datasets/shuyangli94/foodcom-recipes-with-search-terms-and-tags) from Kaggle. 

We explore two approaches for recipe generation:
1. **Chracter-level LSTM language model**, trained from scratch on a large corpus of formatted recipes.
2. **FLAN-T5 model**, fine-tuned using LoRA.

The final system also includes a **retriever model**.

The repository is organised into two main scripts:
- `lstm-model-training.ipynb`: End-to-end LSTM pipeline 
- `flan-t5-model-training.ipynb`: FLAN-T5 and retriever pipeline

Each file is intended to run independently and both provide a full workflow from raw data to model outputs.

## Setup Instructions

1. **Install dependencies**
```bash
pip install -r requirements.txt
```
2. **Run the notebooks**

- `lstm-model-training.ipynb` will train the LSTM model.

- `flan-t5-model-training.ipynb` will fine-tune the FLAN-T5 model and save it  in the `recipe_model/` directory.
