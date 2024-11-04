# Multilingual Question Answering with Rule-Based and Machine Learning Models

This project explores multilingual question answering (QA) with datasets in Japanese, Finnish, and Russian, each paired with English context. We experimented with rule-based, n-gram, and machine learning models to classify questions as answerable/unanswerable.

## Project Structure
- **Data Exploration**: Analyzed language-specific question patterns and tokenized words for common word identification.
- **Models Implemented**:
  - **Rule-Based Classifier**: Checks token overlap between translated questions and context.
  - **N-gram Models**: Bigram and trigram language models for each language, evaluated on perplexity.
  - **Logistic Regression (Bag-of-Words)**: Predicts answerability using tokenized question-context features.
  - **Neural Network with DistilBERT**: Utilizes embeddings to classify answerable questions.
  - **DistilBertForQuestionAnswering**: Trained for span prediction on combined languages.
  - **Multilingual BERT Sequence Labeller**: Token classification for QA, using weighted loss for class imbalance.

## Key Results
| Model                    | Language | Accuracy | TPR (%) | FPR (%) |
|--------------------------|----------|----------|---------|---------|
| **Rule-Based Classifier** | Finnish  | 72%      | 98.51%  | 93.94%  |
| **DistilBERT NN**        | Japanese | 78.95%   | 91.64%  | 42.60%  |
| **Logistic Regression**   | Russian  | 86%      | 87%     | 99%     |
| **BERT QA Model**        | Combined | 44.13% (Exact Match, Finnish) | - | - |

## Usage
1. **Preprocess Data**: Tokenize questions and context, and split into train/validation.
2. **Train Models**: Run models in sequence or selectively based on the configuration.
3. **Evaluate**: Compute metrics like accuracy, F1 score, and perplexity for n-grams.

For detailed instructions and dependencies, see the [installation guide](docs/installation.md).

## References
- **[DistilBERT](https://arxiv.org/abs/1910.01108)**
- **[Jurafsky et al., "Speech and Language Processing"](https://web.stanford.edu/~jurafsky/slp3/)**
