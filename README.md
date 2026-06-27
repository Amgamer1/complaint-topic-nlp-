# Complaint Topic NLP Analysis

This project uses Natural Language Processing techniques to analyze consumer complaint narratives. The goal is to identify common topics in unstructured complaint texts.

## Dataset

The dataset used is the Consumer Financial Protection Bureau Consumer Complaint Database. The main text field used for analysis is the consumer complaint narrative.

## Methods

The workflow includes:

1. Loading the complaint dataset
2. Removing missing and duplicate complaint narratives
3. Cleaning text by removing punctuation, numbers, URLs, and extra spaces
4. Vectorizing the text with:
   - CountVectorizer
   - TF-IDF Vectorizer
5. Extracting topics with:
   - Latent Dirichlet Allocation
   - Non-negative Matrix Factorization
6. Saving topic results and charts in the outputs folder

## How to Run

Install the required libraries:

```bash
pip install -r requirements.txt
