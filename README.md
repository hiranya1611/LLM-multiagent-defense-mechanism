"# LLM-multiagent-defense-mechanism" 
# ARCHIAS v4 — Multi-Agent Defense System for LLM Jailbreak & Injection Attacks

**A Robust Multi-Agent Framework for Detecting & Mitigating Prompt Injections, Price Manipulations, Malicious Queries, and Out-of-Domain Requests in Automotive Chatbots**

[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)
[![Transformers](https://img.shields.io/badge/🤗-Transformers-yellow)](https://huggingface.co/docs/transformers)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## Overview

**ARCHIAS** (Advanced Robust Classifier for Hybrid Injection Attack Shield) is a complete end-to-end system designed to protect LLM-based automotive assistants from:

- **Prompt Injection** (Class 3)
- **Price Injection** (Class 2)
- **Malicious Requests** (Class 1)
- **Out-of-Domain Queries** (Class 4)
- **Legitimate Automotive Queries** (Class 0 – allowed)

### Key Components

| Component          | Version | Purpose |
|--------------------|---------|-------|
| **Classifier**     | v3      | Fine-tuned BERT classifier (5-class) |
| **Multi-Agent Defense** | v4  | Simulator + Integrator agents for jailbreak resistance |
| **Dataset**        | ARCHIAS v3 | 5,000 balanced synthetic + real examples |
| **Model**          | `bert-base-uncased` | Fine-tuned on automotive domain |

**ARCHIAS v4** introduces a **multi-agent simulation layer** that generates adversarial variants of every query and measures **Attack Success Rate (ASR)** — making it significantly harder for jailbreaks to succeed.

---

## Features

- Balanced 5-class dataset generation (fast random sampling)
- Full training pipeline with early stopping & best-model saving
- Multi-agent simulation (8 variants per query)
- Attack Success Rate (ASR) scoring
- Consensus-based decision engine (Allow / Block / Flag / Redirect)
- Audit logging (JSONL)
- Ready for Kaggle / Colab / local deployment
- Domain-specific hard negatives (automotive-related OOD)

---

## Project Structure

```bash
ARCHIAS/
├── archias_v3_dataset.csv                  # Generated dataset
├── archias_v3_hf_dataset/                  # Hugging Face dataset format
├── archias_v3_final/                       # Final trained model
├── archias_v3/                             # Checkpoints (during training)
├── archias_v4.py                           # ← Multi-agent inference system
├── generate_dataset_and_train.py           # Full v3 pipeline
├── README.md
├── requirements.txt
└── archias_audit.jsonl                     # Auto-generated after inference
