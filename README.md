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

## Repository Structure

```
Pantry-Pal/
│  
├── lstm/  
│   └── lstm-model-training.ipynb            # lstm model training
│   └── ckpt_20.weights.h5                   # weights of saved model
│   └── recipe_model.h5                      # saved model in h5 format
│   └── recipe_model.keras                   # saved model in keras format
│  
├── flan-t5/  
│   ├── recipe_model/  
│   │   └── final_model/                     # drop-in path for embedding file and saved models
│   │       └── …                            # weights of saved model
│   └── flan-t5-model-training.ipynb         # FLAN-T5 model and retrieval training
│  
├── .gitignore  
├── README.md  
└── requirements.txt                          # Python dependencies  

```

## Setup Instructions

1. **Install dependencies**
```bash
pip install -r requirements.txt
```

2. **Download file from releases**
`recipe_embeddings.npy` can be found under releases as it is too big to be stored directly in the repository.
- Download `recipe_embeddings.npy` from this release: Pantry-Pal model artifacts (embeddings file)
- Place it in the following folder inside the project:
```bash
flan-t5/recipe_model/final_model/
```
- The final path should look like:
```
flan-t5/recipe_model/final_model/recipe_embeddings.npy
```

3. **Run the notebooks**

- `lstm-model-training.ipynb` will train the LSTM model.

- `flan-t5-model-training.ipynb` will fine-tune the FLAN-T5 model and save it  in the `recipe_model/` directory.
