# Comparative Analysis of Learning Paradigms for Text Classification

## Overview

This project was developed as part of the **Advanced Machine Learning** course at the German International University (GIU).

The objective is to compare three different learning paradigms for text classification on the same six-class emotion recognition task:

- From-Scratch Recurrent Neural Network (GRU)
- Transfer Learning using DistilBERT
- Large Language Model (LLM) Prompting

The goal is to analyze the strengths, weaknesses, computational cost, and data efficiency of each approach rather than simply achieving the highest accuracy.

---

## Dataset

Dataset: **dair-ai/emotion**

The dataset consists of short English texts labeled with one of six emotions:

- Sadness
- Joy
- Love
- Anger
- Fear
- Surprise

Dataset splits:

| Split | Samples |
|--------|---------|
| Train | 16,000 |
| Validation | 2,000 |
| Test | 2,000 |

Dataset Link:
https://huggingface.co/datasets/dair-ai/emotion

---

## Project Structure

```
├── AML3.ipynb              # Main notebook
├── README.md
└── results/
```

The notebook is divided into six main parts:

1. Data Preprocessing & Exploration
2. From-Scratch GRU Classifier
3. Fine-Tuning DistilBERT
4. LLM Prompting
5. Data Efficiency Experiment
6. Comparative Analysis

---

## Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- Hugging Face Datasets
- Scikit-learn
- NumPy
- Pandas
- Matplotlib

---

## Part 1 – Data Preprocessing

The preprocessing stage includes:

- Loading the dataset from Hugging Face
- Dataset inspection
- Class distribution analysis
- Text length analysis
- Visualization of dataset statistics
- Custom tokenizer and vocabulary construction for the GRU model
- Pretrained tokenizer using DistilBERT
- Sequence padding and truncation

---

## Part 2 – From-Scratch GRU Classifier

A recurrent neural network is implemented entirely from scratch using PyTorch.

Model architecture:

- Embedding Layer
- GRU Layer
- Dropout
- Fully Connected Classification Layer

Evaluation metrics:

- Test Accuracy
- Macro F1 Score
- Per-Class F1 Score
- Confusion Matrix
- Training Time
- Inference Time

---

## Part 3 – Transfer Learning

A pretrained DistilBERT model is fine-tuned for emotion classification.

Fine-tuning includes:

- Hugging Face AutoTokenizer
- AutoModelForSequenceClassification
- Trainer API
- Validation during training
- Test evaluation

Performance is compared directly with the GRU baseline.

---

## Part 4 – LLM Prompting

A pretrained instruction-following Large Language Model is evaluated without gradient updates.

Prompting strategies include:

- Zero-shot prompting
- Few-shot prompting
- Chain-of-Thought prompting

Results are evaluated using:

- Accuracy
- Macro F1
- Confusion Matrix
- Inference Time

---

## Part 5 – Data Efficiency Experiment

To study the impact of pretraining, both the GRU model and DistilBERT are retrained using only 500 balanced training samples.

The LLM does not require retraining.

Performance is compared with models trained on the full dataset.

---

## Part 6 – Comparative Analysis

The final section compares all three paradigms based on:

- Accuracy
- Macro F1 Score
- Training Time
- Inference Time
- Data Efficiency
- Failure Cases
- Practical Applications

---

## Results

The project investigates the trade-offs between:

- Traditional supervised learning
- Transfer learning
- Prompt-based inference

The experiments demonstrate how pretrained language models significantly improve performance while reducing the amount of task-specific training data required.

---

## Installation

Install the required packages:

```bash
pip install torch transformers datasets scikit-learn pandas matplotlib
```

---

## Running the Project

1. Clone the repository.

```bash
git clone <repository-url>
```

2. Install the dependencies.

3. Open the notebook.

```bash
jupyter notebook
```

or

```bash
jupyter lab
```

4. Execute the notebook cells sequentially.

---

## Authors

Advanced Machine Learning

German International University (GIU)

Spring 2026

---

## Acknowledgments

- Hugging Face
- DAIR.AI
- PyTorch
- Scikit-learn
