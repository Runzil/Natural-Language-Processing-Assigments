# Evaluating Neural Architectures for Sentence Representation and Sentiment Classification

## Introduction
This project explores neural architectures for sentiment classification on the **Stanford Sentiment Treebank (SST)** dataset. The task involves classifying sentences into one of five sentiment classes: very negative, negative, neutral, positive, and very positive. We evaluate the performance of various models, focusing on the impact of word order, hierarchical structures, and sentence length.

## Models Implemented
### 1. Bag-of-Words (BoW)
- Uses word frequency vectors for sentiment classification.
- Efficient but lacks the ability to capture word order and relationships.

### 2. Continuous Bag-of-Words (CBoW)
- Incorporates word embeddings to improve BoW by capturing semantic relationships.
- Aggregates word embeddings for sentiment prediction.

### 3. DeepCBoW
- Extends CBoW by adding non-linearity through two hidden layers.
- Demonstrates improved performance over simpler BoW models.

### 4. Long Short-Term Memory (LSTM)
- Processes text sequentially, capturing contextual information.
- Utilizes pre-trained GloVe embeddings for improved representation.

### 5. Tree-LSTM
- Captures hierarchical relationships in sentence structures.
- Processes sentences using syntactic parse trees, providing better compositional semantics.

### 6. LSTM with Memory Cell Enhancements (Le & Zuidema)
- Adds cell state connections and enhanced gating mechanisms to traditional LSTMs.
- Competes closely with Tree-LSTM in performance.

## Dataset
The **Stanford Sentiment Treebank (SST)** dataset provides both sentence-level and phrase-level annotations for sentiment analysis. It enables models to capture fine-grained sentiment by leveraging tree-structured syntactic representations.

## Experiments
1. **Word Order Importance**: Comparing sequential models (e.g., LSTM) with unordered approaches (e.g., BoW).
2. **Tree Structure Impact**: Evaluating Tree-LSTMs versus sequential LSTMs.
3. **Sentence Length Impact**: Analyzing model performance on short vs. long sentences.
4. **Model Comparison**: Contrasting Tree-LSTM with Le & Zuidema’s formulation.

## Results
- **BoW**: Fast but limited in capturing complex relationships.
- **CBoW & DeepCBoW**: Improved performance with embeddings and non-linearity.
- **LSTM**: Strong sequential modeling capabilities.
- **Tree-LSTM**: Best performance by leveraging hierarchical structures.
- **LSTM-Zuidema**: Comparable to Tree-LSTM but focuses on gating mechanisms.

| Model                  | Accuracy (Short) | Accuracy (Long) | Overall Accuracy |
|------------------------|------------------|-----------------|------------------|
| BoW                   | 0.255            | 0.277           | 0.267            |
| CBoW                  | 0.366            | 0.341           | 0.353            |
| DeepCBoW              | 0.383            | 0.378           | 0.379            |
| LSTM                  | 0.487            | 0.444           | 0.465            |
| Tree-LSTM             | 0.496            | 0.451           | 0.473            |
| LSTM-Zuidema          | 0.495            | 0.451           | 0.472            |

## Usage
### Prerequisites
- Python 3.6+
- Libraries: `PyTorch`, `NumPy`, `NLTK`


###Conclusion

- **Word Order**: Essential for effective sentiment classification.
- **Tree Structures**: Significantly enhance accuracy by capturing hierarchical relationships.
- **Future Work**: Investigate alternative tree construction strategies and conduct hyperparameter tuning.
