# Complaint Topic NLP Analysis

This project analyzes consumer complaint narratives using Natural Language Processing techniques. The goal is to identify recurring topics in unstructured complaint texts.

## Dataset

The dataset used for this project is based on the Consumer Financial Protection Bureau Consumer Complaint Database.

Dataset source:
Consumer Financial Protection Bureau. Consumer Complaint Database.
https://www.consumerfinance.gov/data-research/consumer-complaints/

Field documentation:
Consumer Financial Protection Bureau. Consumer Complaint Database API documentation: Field reference.
https://cfpb.github.io/api/ccdb/fields.html

The CSV file is not included directly in this GitHub repository. To run the project, the user must download or export the complaint data from the CFPB Consumer Complaint Database and place the file manually inside a folder called `data`.

The required file path is:

`data/CFPB_Consumer_Complaints_2024.csv`

The main text column used for the NLP analysis is:

`consumer_complaint_narrative`

This column contains the written complaint narrative used for topic extraction.

In the dataset used for this project, there were 500 rows and 18 columns. After removing missing and duplicate complaint narratives, 200 texts remained. After text cleaning and filtering very short texts, 173 complaint narratives were used for the final topic analysis.

## Methods

The workflow includes:

1. Loading the complaint dataset with pandas
2. Removing missing and duplicate complaint narratives
3. Cleaning the text by removing URLs, redaction patterns, numbers, punctuation, very short words, and extra spaces
4. Applying English stop words and additional custom stop words
5. Vectorizing the cleaned text with:

   * CountVectorizer
   * TF-IDF Vectorizer
6. Extracting topics with:

   * Latent Dirichlet Allocation
   * Non-negative Matrix Factorization
7. Saving topic results, topic examples, comparison files, and charts in the `outputs` folder

## Results

Both vectorization methods produced a matrix with 173 complaints and 1383 text features.

The topic models showed recurring complaint areas such as identity theft, debt validation, creditor disputes, collection agency contact, owed money, and requests to remove incorrect information.

Some topic overlap remained because the dataset sample was relatively small. However, comparing LDA and NMF helped make the recurring complaint patterns easier to interpret.

## How to Run

First, install the required Python libraries:

```bash
pip install -r requirements.txt
```

Then create a folder called `data` in the project directory and place the CSV file inside it:

```text
data/CFPB_Consumer_Complaints_2024.csv
```

Run the script:

```bash
python main.py
```

The results will be saved automatically in the `outputs` folder.

## Output Files

After running the script, the following files are created:

```text
cleaned_complaints.csv
dataset_overview.txt
lda_topics.csv
nmf_topics.csv
lda_topic_examples.csv
nmf_topic_examples.csv
complaints_with_topics.csv
vectorizer_comparison.csv
lda_topic_distribution.png
nmf_topic_distribution.png
```

## Requirements

The project uses the following Python libraries:

```text
pandas
matplotlib
scikit-learn
```
