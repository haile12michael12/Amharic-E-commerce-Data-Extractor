# 🛍️ EthioMart - Amharic E-commerce Data Extractor & Vendor Scorecard

EthioMart is on a mission to become the unified platform for all Telegram-based e-commerce in Ethiopia. This project leverages the power of NLP and large language models (LLMs) to extract structured data (Product, Price, Location) from unstructured Amharic Telegram messages. It also evaluates vendors’ performance for micro-lending through a data-driven vendor scorecard.

---

## 🚀 Project Goals

- Consolidate product data from multiple Telegram e-commerce channels into one searchable database.
- Fine-tune transformer-based models for Amharic Named Entity Recognition (NER).
- Evaluate and compare different NER models.
- Build vendor profiles and generate a data-backed **FinTech Lending Scorecard**.

---

## 🧱 Project Structure


amharic-ecom-data-extractor/
├── data/
│   ├── raw/                  # Raw scraped messages
│   ├── labeled/              # CoNLL-labeled dataset
│   └── processed/            # Extracted entities (CSV/JSON)
├── media/                    # Product images from Telegram
├── scripts/
│   ├── scraper.py            # Telegram data ingestion
│   ├── preprocess.py         # Amharic text cleaning
│   ├── extract_entities.py   # Inference using fine-tuned NER
│   ├── evaluate_models.py    # Model comparison
│   ├── interpretability.py   # SHAP/LIME explanation
│   └── vendor_scorecard.py   # Vendor analytics engine
├── notebooks/
│   └── ner_finetuning.ipynb  # HuggingFace fine-tuning notebook
├── models/                   # Saved fine-tuned model(s)
├── requirements.txt
├── README.md
└── .gitignore


📌 Tasks Overview
✅ Task 1: Data Ingestion & Preprocessing
Scrape text and images from 5+ Telegram e-commerce channels using telethon.

Preprocess Amharic messages: normalize, clean, tokenize.

Store with metadata (timestamp, sender, media_type).

✅ Task 2: NER Data Labeling (CoNLL Format)
Label 30–50 Amharic messages manually with:

B-Product, B-PRICE, B-LOC, optional: B-DELIVERY_FEE, B-CONTACT_INFO

Save in labeled_data.conll format.

✅ Task 3: Fine-tune NER Model
Use XLM-Roberta, bert-tiny-amharic, or AfroXLM-R.

Load CoNLL data, tokenize, align labels.

Fine-tune using HuggingFace Trainer on GPU (Colab).

Save final model under /models.

✅ Task 4: Model Comparison & Selection
Compare XLM-R, mBERT, and DistilBERT.

Metrics: F1, Precision, Recall, Inference Speed.

Recommend the best model for EthioMart.

✅ Task 5: Model Interpretability
Apply SHAP and LIME to visualize and explain entity decisions.

Diagnose ambiguous cases and identify model behavior patterns.

✅ Task 6: Vendor Scorecard for Micro-Lending
Analyze each vendor’s:

Post frequency (per week)

Avg. views per post

Avg. product price

Top product performance