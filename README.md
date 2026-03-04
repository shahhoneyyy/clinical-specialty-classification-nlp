# Clinical Specialty Classification from Medical Transcriptions

## Problem

Clinical transcription reports contain rich medical information but are unstructured and difficult to analyze automatically.

This project builds machine learning models to classify medical specialties directly from raw clinical transcription text.

## Dataset

MTSamples dataset  
1,000 medical transcription reports across multiple specialties.

Each record includes:

- medical specialty
- transcription text
- keywords
- description

## Objective

Compare two NLP approaches:

1. Text-only classification using TF-IDF features
2. Hybrid model combining TF-IDF with UMLS clinical concepts

The goal is to evaluate whether medical knowledge graphs improve classification performance.

## NLP Pipeline

Text preprocessing included:

- Unicode normalization
- Lowercasing
- Punctuation removal
- Stopword filtering
- Lemmatization using spaCy
- De-identification of numbers and IDs

Output text column: `transcription_normalized`

## Models Tested

- Multinomial Naive Bayes
- Logistic Regression
- Linear Support Vector Classifier

Feature representation:

- TF-IDF
- TF-IDF + UMLS Concept Identifiers

## Results

Best Text-Only Model  
Multinomial Naive Bayes

Accuracy: ~0.645  
Macro F1: ~0.626

Hybrid UMLS + Text Model

Accuracy: ~0.650  
Macro F1: ~0.634

Adding UMLS concepts produced small but consistent improvements in classification performance.

## Key Insights

Medical transcriptions contain heavy vocabulary overlap across specialties.

TF-IDF captures surface terminology but struggles with synonyms and clinical meaning.

UMLS concept extraction helps unify medical terminology and improves model understanding of clinical language.

## Limitations

Small dataset size (1,000 reports)

Long procedural transcriptions create noisy feature spaces.

TF-IDF models cannot capture deep contextual semantics.

## Future Improvements

Use transformer-based medical language models such as BioClinicalBERT.

Combine embeddings with UMLS features.

Expand dataset using larger clinical corpora.

## Project Structure

notebooks/ → full NLP pipeline and model training

data/ → dataset instructions

reports/ → project presentation

assets/ → visualization screenshots


## Tools

Python  
scikit-learn  
spaCy  
UMLS  
NLP  
Machine Learning
