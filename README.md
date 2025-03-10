# Diary Generation using N-Gram Models

## Overview
This project implements a diary entry generator using Unigram, Bigram, and Trigram language models. The model is trained on a given corpus in Roman Urdu and generates diary-like text entries based on learned probabilities.

## Features
- **Data Preprocessing**:
  - Removes numbers, punctuation, and normalizes Roman Urdu text.
  - Converts text to lowercase for consistency.
- **N-Gram Models**:
  - Unigram, Bigram, and Trigram models are implemented from scratch.
  - Probability distributions are calculated for predicting the next word.
- **Diary Entry Generation**:
  - Starts with a randomly chosen word from a predefined list (`start_words`).
  - Generates entries between 7-12 words using Bigram and Trigram probabilities.
- **Perplexity Evaluation**:
  - Measures how well the models predict unseen text.

## Installation
### Prerequisites
Ensure you have Python 3.x installed.

### Clone the Repository
```sh
git clone https://github.com/yourusername/diary-generation-ngram.git
cd diary-generation-ngram
```

## Usage
### Train the N-Gram Models
```python
from train_model import TrainNGramModels
trainer = TrainNGramModels("corpus.txt")  # Load the corpus
trainer.train_unigram()
trainer.train_bigram()
trainer.train_trigram()
```

### Generate a Diary Entry
```python
from diary_generator import DiaryGenerator
import random

diary_generator = DiaryGenerator(trainer.bigram_model, trainer.trigram_model, start_words=["aaj", "raat", "kal", "subha", "shaam", "jab"])
print(diary_generator.generate_diary_entry())
```

### Evaluate Model Perplexity
```python
from evaluate_model import evaluate_perplexity
perplexity = evaluate_perplexity(trigram_model, test_corpus)
print(f"Trigram Model Perplexity: {perplexity}")
```

## Future Enhancements
- Implement backoff techniques for better predictions.
- Use a larger and more diverse corpus for improved fluency.
- Implement a web interface for diary generation.

