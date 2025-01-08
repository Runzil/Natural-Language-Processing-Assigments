# Sentiment Analysis for Movie Reviews

## Table of Contents
- [Introduction](#introduction)
- [Approaches](#approaches)
  - [Lexicon Based Approach](#Lexicon-Based-Approach)
  - [Naive Bayes Classifier](#naive-bayes-classifier)
  - [Support Vector Machine (SVM)](#support-vector-machine-svm)
- [Results](#results)
- [Conclusion](#conclusion)



## Introduction
This project focuses on sentiment analysis for movie reviews, employing various natural language processing (NLP) techniques. The goal is to classify movie reviews as either positive or negative using different models, including:

1. **Lexicon-Based Approach**
2. **Naive Bayes Classifier**
3. **Support Vector Machine (SVM)**

Each approach is implemented and evaluated for performance, showcasing its strengths and limitations.

---

## Approaches

### 1. Lexicon Based Approach
This model uses a predefined lexicon of positive and negative words to determine the sentiment of a document. Each word is scored, and the sentiment is derived by summing the scores across the document. While efficient, it has limitations in capturing contextual nuances.

### 2. Naive Bayes Classifier
We experimented with multiple configurations:
- **Basic Naive Bayes**: Initial implementation without enhancements.
- **Laplace Smoothing**: Applied but did not yield performance improvements.
- **N-Gram Features**: Using unigrams, bigrams, and trigrams, where unigrams + bigrams showed the best accuracy.
- **Stemming**: Tested but did not improve results, indicating sufficient feature capture without it.

### 3. Support Vector Machine (SVM)
The SVM model outperformed Naive Bayes due to its ability to find optimal decision boundaries. Enhancements included:
- Adding Part-of-Speech (POS) tags.
- Focusing on content words (nouns, verbs, adjectives, adverbs).
- Excluding closed-class words (e.g., prepositions) to reduce noise.

The final model (content words + POS tags) achieved the highest accuracy.

---

## Dataset
The dataset comprises 1000 positive and 1000 negative movie reviews, each representing a document with one or more sentences. It can be downloaded [here](https://gist.githubusercontent.com/bastings/d47423301cca214e3930061a5a75e177/raw/5113687382919e22b1f09ce71a8fecd1687a5760/reviews.json).

---

## Usage

### Prerequisites
- Python 3.6+
- Required Python libraries: `scikit-learn`, `nltk`, `numpy`, `pandas`

### Running the Notebook
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/sentiment-analysis.git
   ```
2. Navigate to the project directory and open the notebook:
   ```bash
   cd sentiment-analysis
   jupyter notebook CodeReport.ipynb
   ```
3. Follow the instructions in the notebook to run the experiments.

---

## Results
### Key Observations:
- **Lexicon-Based Approach**: Efficient but less accurate in handling complex language constructs.
- **Naive Bayes**: Benefits from n-gram features but not from stemming or smoothing.
- **SVM**: Achieves the best accuracy with refined feature engineering, leveraging content words and POS tags.

---

## References
1. Bo Pang, Lillian Lee, and Shivakumar Vaithyanathan (2002). "[Thumbs up? Sentiment Classification using Machine Learning Techniques](https://dl.acm.org/citation.cfm?id=1118704)." EMNLP.

---

Feel free to explore and extend this work for advanced NLP techniques like neural networks or transformer-based models!

