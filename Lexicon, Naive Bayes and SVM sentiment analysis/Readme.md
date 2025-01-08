# Sentiment Analysis of Movie Reviews

This project focuses on sentiment analysis using three distinct approaches: a Lexicon-based model, a Naive Bayes classifier, and a Support Vector Machine (SVM). The analysis is performed on a movie review dataset to evaluate the effectiveness of each method and explore their strengths and limitations.

## Table of Contents
- [Introduction](#introduction)
- [Approaches](#approaches)
  - [Lexicon-Based Approach](#lexicon-based-approach)
  - [Naive Bayes Classifier](#naive-bayes-classifier)
  - [Support Vector Machine (SVM)](#support-vector-machine-svm)
- [Results](#results)
- [Conclusion](#conclusion)

## Introduction

Sentiment analysis is a crucial task in Natural Language Processing (NLP) that involves determining the sentiment (positive or negative) of a given text. This project applies three approaches to analyze movie reviews, comparing their performance and discussing their respective advantages and challenges.

## Approaches

### Lexicon-Based Approach

The Lexicon-based approach offers a straightforward sentiment analysis technique:
- Each word in the text is evaluated as either positive or negative.
- The sentiment score is determined by summing these values to infer the overall sentiment of the document.

**Strengths**:
- Simple and computationally efficient.

**Limitations**:
- Struggles to capture contextual nuances.
- Does not account for word frequency or complex sentiment expressions.

### Naive Bayes Classifier

The Naive Bayes classifier experiments with various enhancements to improve sentiment prediction:
1. **Baseline Model**: A simple Naive Bayes classifier.
2. **Laplace Smoothing**: Attempted to handle unseen words but showed no improvement in accuracy.
3. **Stemming**: Did not enhance the model's performance.
4. **N-grams**: Adding bigrams improved accuracy slightly, highlighting the benefit of contextual word relationships. However, including trigrams did not yield additional improvements.

**Key Observation**: Unigrams + bigrams achieved higher accuracy compared to adding trigrams.

### Support Vector Machine (SVM)

The SVM classifier showed superior performance by leveraging high-dimensional feature spaces:
1. **Baseline Model**: Trained using basic word features.
2. **Enhancements**:
   - Added Part-of-Speech (POS) tags.
   - Focused on content words (nouns, verbs, adjectives, adverbs).

**Key Findings**:
- Focusing on sentiment-relevant features (content words) significantly improved performance.
- Incorporating POS tags reduced feature ambiguity and enhanced accuracy.

The final SVM model (content words + POS tags) achieved the highest test accuracy.

## Results

| Approach                | Key Enhancements             | Performance Summary                           |
|-------------------------|------------------------------|----------------------------------------------|
| Lexicon-Based Model     | N/A                          | Efficient but less accurate for nuanced cases. |
| Naive Bayes Classifier  | N-grams (bigrams)            | Improved accuracy with contextual features.   |
| Support Vector Machine  | Content words + POS tags     | Achieved highest accuracy with focused features. |

## Conclusion

This project highlights the strengths and weaknesses of different sentiment analysis methods:

 - The Lexicon-based approach provides an efficient baseline but lacks contextual understanding.
 - The Naive Bayes classifier benefits from n-gram features but has limited adaptability to complex data.
 - SVM achieves superior accuracy by leveraging sentiment-relevant features and reducing noise.