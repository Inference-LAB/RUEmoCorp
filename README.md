# RUEmoCorp: Roman Urdu Emotion Corpus

<div align="center">

[![Harvard Dataverse DOI](https://img.shields.io/badge/Dataverse-10.7910%2FDVN%2FBPWHOZ-orange.svg?style=for-the-badge&logo=harvard)](https://doi.org/10.7910/DVN/BPWHOZ)
[![Research Square Preprint](https://img.shields.io/badge/Research%20Square-10.21203%2Frs.3.rs--9759243%2Fv1-blue.svg?style=for-the-badge&logo=researchgate)](https://www.researchsquare.com/article/rs-9759243/v1)
[![Hugging Face Hub](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Inference--LAB%2FRUEmoCorp-yellow.svg?style=for-the-badge)](https://huggingface.co/Inference-LAB)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)
[![Corpus Size](https://img.shields.io/badge/Corpus%20Size-28%2C010%20%2B%20700-purple.svg?style=for-the-badge)](#corpus-statistics--dataset-quality)
[![Kappa](https://img.shields.io/badge/Fleiss'%20Kappa-%CE%BA%20%3D%200.6588-brightgreen.svg?style=for-the-badge)](#annotation-quality--validation)
[![Model SOTA](https://img.shields.io/badge/Model%20Macro--F1-0.9896-red.svg?style=for-the-badge)](#state-of-the-art-model--benchmark-performance)

<p align="center">
  <strong>The Largest Expert-Annotated Natural Language Processing Dataset and Evaluation Benchmark Suite for Emotion Classification in Roman Urdu.</strong>
</p>

</div>

---

## 📌 Table of Contents
- [Overview & Background](#-overview--background)
- [Key Features](#-key-features)
- [Corpus Statistics & Dataset Quality](#-corpus-statistics--dataset-quality)
- [Emotion Taxonomy & Class Definitions](#-emotion-taxonomy--class-definitions)
- [Annotation Quality & Validation](#-annotation-quality--validation)
- [State-of-the-Art Model & Benchmark Performance](#-state-of-the-art-model--benchmark-performance)
- [Repository Structure](#-repository-structure)
- [Quickstart & Usage](#-quickstart--usage)
  - [Loading the Dataset](#1-loading-the-dataset-hugging-face-datasets)
  - [Running Inference with SOTA Model](#2-running-inference-with-roman-urdu-emotion-xlmr-v2)
- [External Resources & Archives](#-external-resources--archives)
- [Contributors & Roles](#-contributors--roles)
- [Citation](#-citation)
- [License](#-license)

---

## 📖 Overview & Background

**Roman Urdu**—Urdu transcribed using the Latin alphabet rather than the standard Perso-Arabic script—is the predominant medium of informal digital communication across Pakistan and South Asia, with over 230 million native/fluent speakers interacting across messaging apps, social networks, and community forums. 

Despite its pervasive usage, Roman Urdu has historically suffered as an extreme **low-resource language** in Affective Computing and Natural Language Processing (NLP) due to:
1. **Absence of Standardized Orthography**: Non-uniform spellings for identical words (e.g., *"muhabbat"*, *"mohabbat"*, *"mhbt"*).
2. **Heavy Code-Switching & Code-Mixing**: Spontaneous intermixing of English, Urdu, and regional vernaculars.
3. **Severe Scarcity of High-Quality Labeled Data**: Prior datasets were constrained by small sample sizes, lack of neutral/none baselines, or noisy unverified annotations.

**RUEmoCorp (Roman Urdu Emotion Corpus)** resolves these bottlenecks by introducing the largest, expert-annotated, rigorously validated corpus and benchmark suite designed specifically for emotion classification and affective text analysis in Roman Urdu.

---

##  Key Features

* **Massive Scale**: Features a curated training set of **28,010 utterances** and an independently validated **700-sample standardized evaluation benchmark suite**.
* **Ekman-Grounded Taxonomy**: Incorporates Paul Ekman's 6 universal basic emotions (*Joy*, *Anger*, *Sadness*, *Fear*, *Disgust*, *Surprise*) coupled with an explicit **None (Neutral)** baseline class to suppress false-positive classifications on objective/neutral content.
* **Rigorous Multi-University Annotation**: Labeled by independent native-speaker annotators across multiple Pakistani academic institutions, achieving a **Fleiss' Kappa ($\kappa$) of 0.6588** (Substantial Agreement).
* **State-of-the-Art Baseline**: Powers the transformer model [`roman-urdu-emotion-xlmr-v2`](https://huggingface.co/Inference-LAB), reaching a **Macro-averaged F1 score of 0.9896**.
* **Permanent Scientific Archival**: Archived on **Harvard Dataverse** and indexed on **Research Square**.

---

## 📊 Corpus Statistics & Dataset Quality

| Metric | Specification |
| :--- | :--- |
| **Total Curated Training Samples** | 28,010 utterances |
| **Standardized Benchmark Test Suite** | 700 verified samples |
| **Target Language / Script** | Roman Urdu (Latin transliteration of Urdu) |
| **Emotion Classes** | 7 classes (6 basic universal emotions + 1 neutral) |
| **Inter-Annotator Agreement** | $\kappa = 0.6588$ (Fleiss' Multi-Rater Kappa — Substantial) |
| **Primary Domain Sources** | Social media streams, user reviews, digital forums, messaging platforms |
| **Data Quality Framework** | Cross-institute validation, deduplication, phonetic normalization, noise cleansing |

---

## 🏷️ Emotion Taxonomy & Class Definitions

RUEmoCorp maps utterances into seven distinct affective categories:

| Label ID | Emotion | Description | Representative Roman Urdu Example | English Translation |
| :---: | :--- | :--- | :--- | :--- |
| `0` | **Joy** (*Khushi*) | Feelings of happiness, celebration, delight, or gratitude. | *"Bohat zabardast khabar suni aaj, dil khush ho gaya!"* | *"Heard amazing news today, my heart is so happy!"* |
| `1` | **Anger** (*Gussa*) | Frustration, rage, resentment, or hostility. | *"Yeh service intehai bekaar hai, baar baar band ho jati hai!"* | *"This service is utterly useless, it disconnects repeatedly!"* |
| `2` | **Sadness** (*Udaasi*) | Sorrow, grief, disappointment, or loneliness. | *"Sab kuch khatam ho gaya, ab koi umeed baqi nahi rahi."* | *"Everything is finished, no hope remains now."* |
| `3` | **Fear** (*Khauf*) | Anxiety, apprehension, panic, or terror. | *"Mujhe lagta hai koi bara masla hone wala hai, bohat dar lag raha hai."* | *"I feel a huge problem is coming, I am really scared."* |
| `4` | **Disgust** (*Nafrat / Gheen*) | Revulsion, severe distaste, aversion, or disdain. | *"Kitni gandi harkat hai, dekh kar hi ghin aati hai."* | *"What a disgusting act, it repulses me just looking at it."* |
| `5` | **Surprise** (*Hairat*) | Astonishment, unexpected revelations, shock, or wonder. | *"Arey! Yeh achanak kab aur kaise ho gaya?"* | *"Whoa! When and how did this happen so suddenly?"* |
| `6` | **None** (*Neutral*) | Objective statements, factual queries, and emotionally unbiased text. | *"Kal subah 9 bajey meeting start hogi room number 4 mein."* | *"Tomorrow morning at 9 AM the meeting will start in room 4."* |

---

## 🔬 Annotation Quality & Validation

To ensure gold-standard reliability and reproducibility:
1. **Multi-Institutional Annotator Pool**: Independent native-speaker annotators from multiple universities in Pakistan were trained on standardized annotation guidelines.
2. **Inter-Annotator Reliability**: Measured using Fleiss' Multi-Rater Kappa ($\kappa$), achieving **$\kappa = 0.6588$**, representing substantial agreement according to Landis & Koch benchmarks.
3. **Disagreement Resolution & Adjudication**: Ambiguous cases or edge-case code-switched phrases were subjected to expert panel adjudication to eliminate labeling drift.
4. **Lexical & Orthographic Cleansing**: Noise tokens, URL artifacts, and platform-specific symbols were sanitized while preserving critical Roman Urdu colloquial phonetic structures.

---

## ⚡ State-of-the-Art Model & Benchmark Performance

RUEmoCorp serves as the foundational benchmark for fine-tuning multilingual and cross-lingual transformer architectures. The companion model [`roman-urdu-emotion-xlmr-v2`](https://huggingface.co/Inference-LAB) (adapted from XLM-RoBERTa) establishes state-of-the-art performance on the validated 700-sample test suite:

| Model Architecture | Base Model | Macro Precision | Macro Recall | Macro F1-Score | Accuracy |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **`roman-urdu-emotion-xlmr-v2`** | **XLM-RoBERTa** | **0.9898** | **0.9895** | **0.9896** | **98.96%** |
| mBERT Baseline | `bert-base-multilingual-cased` | 0.8921 | 0.8845 | 0.8882 | 89.10% |
| RoBERTa Baseline | `roberta-base` | 0.8650 | 0.8570 | 0.8609 | 86.40% |
| BiLSTM + FastText | Custom Embeddings | 0.7934 | 0.7812 | 0.7872 | 79.05% |

---

## 📁 Repository Structure

```text
RUEmoCorp/
├── README.md                 # Comprehensive project overview, benchmarks & guides
├── LICENSE                   # Open-source license (MIT)
├── citations.tiff            # Harvard Dataverse file & dataset citation records
├── CITATION.cff              # Machine-readable GitHub citation format
├── CITATION.bib              # Standard BibTeX citation file
└── data/                     # Benchmark suite and sample dataset assets
```

---

## 🚀 Quickstart & Usage

### 1. Loading the Dataset (Hugging Face Datasets)

```python
from datasets import load_dataset

# Load RUEmoCorp directly from Hugging Face
dataset = load_dataset("Inference-LAB/RUEmoCorp")

print(dataset)
# Example utterance:
# {'text': 'Ajj ka din bohat zabardast guzra!', 'label': 'joy', 'label_id': 0}
```

### 2. Running Inference with `roman-urdu-emotion-xlmr-v2`

```python
from transformers import AutoTokenizer, AutoModelForSequenceClassification, pipeline

# Load pre-trained model and tokenizer
model_name = "Inference-LAB/roman-urdu-emotion-xlmr-v2"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForSequenceClassification.from_pretrained(model_name)

# Initialize classification pipeline
classifier = pipeline("text-classification", model=model, tokenizer=tokenizer)

# Test with Roman Urdu utterances
samples = [
    "Bohat khushi hui aap ki kamiyabi dekh kar!",
    "Mujhe yeh harkat bilkul pasand nahi aayi, intehai fazool hai.",
    "Kya kal class hogi ya chutti hai?"
]

results = classifier(samples)
for text, result in zip(samples, results):
    print(f"Text: {text}\nPrediction: {result['label']} (Confidence: {result['score']:.4f})\n")
```

---

## 🌐 External Resources & Archives

* 🏛️ **Harvard Dataverse Repository**: [https://doi.org/10.7910/DVN/BPWHOZ](https://doi.org/10.7910/DVN/BPWHOZ)
* 📄 **Research Square Preprint**: [RUEmoCorp: A Large-Scale Roman Urdu Corpus and Benchmark Suite for Emotion Classification](https://www.researchsquare.com/article/rs-9759243/v1)
* 🤗 **Hugging Face Hub**: [Inference-LAB on Hugging Face](https://huggingface.co/Inference-LAB)
* 🏢 **Organization Website**: [INFERENCE Lab](https://github.com/Inference-LAB)

---

## 👥 Contributors & Roles

| Contributor | Roles & Responsibilities | Affiliation |
| :--- | :--- | :--- |
| **Muhammad Khubaib Ahmad** | Core Researcher, Lead Engineer, Project Administration, Model Development | INFERENCE Lab |
| **Khadija Faisal** | Data Manager, Annotation Coordination, Annotator | INFERENCE Lab |
| **Muzammil Shadab** | Independent Annotator & Validation | INFERENCE Lab |
| **Sara** | Independent Annotator & Quality Control | Collaborative Partner |
| **Faiez Ahmad** | Independent Annotator & Benchmark Reviewer | Collaborative Partner |

---

## 📚 Citation

If you use **RUEmoCorp** or the **`roman-urdu-emotion-xlmr-v2`** model in your research, please cite our work using the following references:

### Dataset Citation (Harvard Dataverse)
> Ahmad, M. K., & Faisal, K. (2025). *RUEmoCorp: Roman Urdu Emotion Corpus* [Data set]. Harvard Dataverse. https://doi.org/10.7910/DVN/BPWHOZ

### Research Paper Citation (Research Square Preprint)
> Ahmad, M. K., Faisal, K., et al. (2026). *RUEmoCorp: A Large-Scale Roman Urdu Corpus and Benchmark Suite for Emotion Classification*. Research Square. https://doi.org/10.21203/rs.3.rs-9759243/v1

### BibTeX Format

```bibtex
@data{DVN/BPWHOZ_2026,
  author    = {Ahmad, Muhammad Khubaib and Faisal, Khadija},
  publisher = {Harvard Dataverse},
  title     = {{RUEmoCorp: Roman Urdu Emotion Corpus}},
  UNF       = {UNF:6:h03jo4SJGEAKuZCik1R/Bw==},
  year      = {2026},
  version   = {V2},
  doi       = {10.7910/DVN/BPWHOZ},
  url       = {https://doi.org/10.7910/DVN/BPWHOZ}
}

@article{Ahmad_RUEmoCorp_2026,
  author    = {Ahmad, Muhammad Khubaib and Faisal, Khadija and Shadab, Muzammil and Sara and Ahmad, Faiez},
  title     = {{RUEmoCorp: A Large-Scale Roman Urdu Corpus and Benchmark Suite for Emotion Classification}},
  journal   = {Research Square},
  year      = {2026},
  doi       = {10.21203/rs.3.rs-9759243/v1},
  url       = {https://www.researchsquare.com/article/rs-9759243/v1}
}
```

---

## 📄 License

This repository and dataset are distributed under the **MIT License**. See the [LICENSE](LICENSE) file for complete details.

---
<div align="center">
  <sub>Developed by <a href="https://github.com/Inference-LAB">INFERENCE Lab</a>. For inquiries or collaboration, please reach out via GitHub issues or email.</sub>
</div>
