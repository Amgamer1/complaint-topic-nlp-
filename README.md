# Complaint Topic NLP Analysis

This project analyzes consumer complaint narratives using Natural Language Processing techniques. The goal is to identify recurring topics in unstructured complaint texts.

## Dataset

The dataset used is `CFPB_Consumer_Complaints_2024.csv`. The main text column used for the analysis is `consumer_complaint_narrative`.

The dataset contained 500 rows and 18 columns. After removing missing and duplicate complaint narratives, 200 texts remained. After text cleaning and filtering very short texts, 173 complaint narratives were used for the final analysis.

## Methods

The workflow includes:

1. Loading the complaint dataset with pandas
2. Removing missing and duplicate complaint narratives
3. Cleaning the text by removing URLs, redaction patterns, numbers, punctuation, very short words, and extra spaces
4. Applying English and custom stop words
5. Vectorizing the cleaned text with:
   - CountVectorizer
   - TF-IDF Vectorizer
6. Extracting topics with:
   - Latent Dirichlet Allocation
   - Non-negative Matrix Factorization
7. Saving topic results, examples, and charts in the `outputs` folder

## Results

Both vectorization methods produced a matrix with 173 complaints and 1383 text features.

The topic models showed recurring complaint areas such as identity theft, debt validation, creditor disputes, collection agency contact, owed money, and requests to remove incorrect information.

## How to Run

Install the required libraries:

```bash
pip install -r requirements.txt
