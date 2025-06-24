# Readme of Assignment 2.1
# Assignment 2.1: Text Vectorization Implementation

## Overview
This project implements the TF-IDF algorithm from scratch and compares it with scikit-learn's CountVectorizer and TfidfVectorizer.

## Implementation Details

### Manual TF-IDF Algorithm
- *Term Frequency (TF)*: tf(t,d) = count(t,d) / |d|
- *Inverse Document Frequency (IDF)*: idf(t) = log(N / df(t))
- *TF-IDF*: tfidf(t,d) = tf(t,d) × idf(t)

### Key Findings

1. *Score Differences*: Manual implementation produces different scores than scikit-learn's TfidfVectorizer due to:
   - *Normalization*: Scikit-learn applies L2 normalization by default
   - *Smoothing*: Different smoothing techniques in the IDF calculation
   - *Formula variations*: Slight implementation differences

2. *Common Words Analysis*: 
   - Words like "the" have low TF-IDF scores because:
     - High term frequency (TF) in individual documents
     - Low inverse document frequency (IDF) due to appearing in multiple documents
     - The IDF component heavily penalizes common words

3. *CountVectorizer vs TF-IDF*:
   - CountVectorizer shows raw term frequencies
   - TF-IDF weighs terms by their importance across the corpus
   - Rare words get higher TF-IDF scores than common words

## Results Summary
The manual implementation successfully demonstrates the core TF-IDF concept, with differences from scikit-learn primarily due to normalization and implementation details rather than algorithmic errors.
