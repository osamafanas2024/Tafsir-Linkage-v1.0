# 📖 Tafsir-SBERT: Semantic Modeling of Exegetical Relatedness Between Quranic Verses
# 📖 النمذجة الدلالية للترابط التفسيري بين الآيات القرآنية

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?&logo=PyTorch&logoColor=white)](https://pytorch.org/)
[![Model](https://img.shields.io/badge/SBERT-Sentence%20Transformers-orange)](https://www.sbert.net/)
[![Fine-Tuning](https://img.shields.io/badge/QLoRA-Parameter%20Efficient-green)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 🌍 Overview | نبذة عن المشروع

**English:** This repository hosts the codebase, datasets, and fine-tuned models for **Tafsir-Linkage-v1.0**, a pioneering Ph.D. research initiative. The project bridges the gap between state-of-the-art Artificial Intelligence (AI) and Classical Islamic Sciences (*Usul Al-Tafsir*). Unlike traditional Natural Language Processing (NLP) models that merely measure surface-level semantic similarity, Tafsir-Linkage-v1.0 is fine-tuned to understand and classify the **functional exegetical relationships** between Quranic verses, strictly adhering to the methodology of master exegetes (e.g., Ibn Kathir).

**بالعربية:** يضم هذا المستودع الشيفرات البرمجية، مجموعات البيانات، والنماذج المُدربة لمشروع **Tafsir-SBERT**، وهو مبادرة بحثية رائدة ضمن أطروحة الدكتوراه. يهدف المشروع إلى مد الجسر بين أحدث تقنيات الذكاء الاصطناعي وعلوم التفسير وأصوله. بخلاف نماذج معالجة اللغات الطبيعية التقليدية التي تقيس التشابه الدلالي السطحي، تم ضبط هذا النموذج بدقة لفهم وتصنيف **العلاقات التفسيرية الوظيفية** بين الآيات القرآنية، استناداً إلى منهجية أئمة التفسير (مثل الإمام ابن كثير).

---

## 🎯 Research Objectives | أهداف البحث

The core objective is to move from standard "Information Retrieval" to "Semantic Classification", automating the detection of specific Usuli relationships through a quaternary schema:

الهدف الأساسي هو الانتقال من مجرد "استرجاع المعلومات" إلى "التصنيف الدلالي العميق"، عبر أتمتة كشف العلاقات التفسيرية وفق تصنيف رباعي دقيق:

- **[BYN] Bayān / البيان (Exposition):** *A verse that explains a general or ambiguous concept in another.* آية تُبيِّن مفهوماً مُجمَلاً في آية أخرى.

- **[TKS] Takhṣīṣ / التخصيص (Specification):** *A verse that restricts a general ruling found in another.* آية تُخصِّص حكماً عاماً ورد في آية أخرى.

- **[STD] Istidlāl / الاستدلال (Citation):** *A verse that cites or serves as evidence for another.* آية تَستشهد بأخرى أو تُتخذ دليلاً عليها.

- **[NDR] Naẓīr / النظير (Parallel):** *Two parallel or highly similar verses in meaning or structure.* آيتان متماثلتان أو متقاربتان جداً في المعنى أو السياق.

---

## 🛠️ Technical Architecture | المعمارية التقنية

This project leverages cutting-edge NLP methodologies to handle the complex semantic and morphological structure of the Classical Arabic found in the Quran.

يعتمد المشروع على أحدث منهجيات معالجة اللغات الطبيعية للتعامل مع البنية الدلالية والصرفية المعقدة للغة العربية التراثية في القرآن الكريم.

1. **Base Model (النموذج الأساسي):** Based on **Sentence-BERT (SBERT)** (e.g., `AraBERT` or `paraphrase-multilingual-MiniLM-L12-v2`) to generate high-quality, context-aware embeddings.
2. **Fine-Tuning Technique (تقنية الضبط الدقيق):** Utilizes **QLoRA (Quantized Low-Rank Adaptation)**. By freezing the base model and training 16-bit LoRA adapters over NF4 quantized weights, we achieve high-precision multi-class classification on consumer-grade GPUs while avoiding catastrophic forgetting.
3. **Loss Function (دالة التكلفة):** Customized **Cross-Entropy Loss** optimized for multi-class textual entailment and relationship prediction.

---

## 🚀 Quick Start | البدء السريع

### 1. Installation | التثبيت
Clone the repository and install the required dependencies:
```bash
git clone [https://github.com/YourUsername/Tafsir-SBERT.git](https://github.com/YourUsername/Tafsir-SBERT.git)
cd Tafsir-SBERT
pip install -r requirements.txt
