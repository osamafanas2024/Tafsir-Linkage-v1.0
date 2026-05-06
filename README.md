# Tafsir-Linkage-v1.0
Advancing Quranic Semantics: Fine-Tuning SBERT via QLoRA for Exegetical Verse Relationship Classification (BYN/TKS/STD/NDR).

This repository contains the code, data, and models for the Ph.D. research project: **"Tafsir-Linkage-v1.0"**. 
The project aims to advance computational Quranic semantics by moving beyond surface-level keyword matching to deep, principled exegetical classification based on classical Islamic principles (Usul Al-Tafsir).

---

## 🎯 Research Objective
Traditional Quranic retrieval models detect general similarity. **Tafsir-SBERT** acts as an AI-driven Usuli scholar, fine-tuning state-of-the-art Transformer models to classify the *exact* exegetical relationship between two verses, primarily focusing on:
- **[BYN] Bayān (Clarification):** A verse explaining another.
- **[TKS] Takhṣīṣ (Specification):** A verse restricting the general ruling of another.

## 🛠️ Architecture & Methodology
- **Base Model:** Sentence-BERT (`paraphrase-multilingual-MiniLM-L12-v2` / `AraBERT`).
- **Fine-Tuning Technique:** **QLoRA** (Quantized Low-Rank Adaptation).
- **Optimization:** We utilize NF4 quantization and 16-bit LoRA adapters to ensure efficient training on consumer-grade GPUs without catastrophic forgetting of the Arabic morphological base.
- **Dataset:** Curated pairs extracted directly from *Tafsir Ibn Kathir*, annotated based on Dr. Al-Mutairi's classification of *Tafsir of the Quran by the Quran*.

## 🚀 Quick Start

### 1. Installation
Clone the repository and install the dependencies:
```bash
git clone [https://github.com/YourUsername/Tafsir-SBERT.git](https://github.com/YourUsername/Tafsir-SBERT.git)
cd Tafsir-SBERT
pip install -r requirements.txt
