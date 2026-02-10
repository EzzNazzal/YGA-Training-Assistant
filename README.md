# YGA Training Assistant (HTU) 🎓🤖

**Developer:** EzzEdden Nazzal  
**Program:** Generative AI Training (HTU)

![Status](https://img.shields.io/badge/Status-Live-success) ![Stack](https://img.shields.io/badge/Stack-n8n%20|%20Supabase%20|%20OpenAI-blue) ![License](https://img.shields.io/badge/License-MIT-green)

## 📖 Overview
The **YGA Training Assistant** is an automated **Retrieval-Augmented Generation (RAG)** system designed to handle Tier-1 student support for the Al Hussein Technical University (HTU) training program.

It alleviates the operational bottleneck faced by the administration (Ms. Zain) by autonomously handling repetitive queries about schedules, admissions, and policies across four technical tracks. If the AI is unsure, it escalates the ticket to a human via Google Sheets and **learns from the answer automatically**.

### Key Features
* **Multi-Channel:** Accessible via **Telegram** and **Web Widget**.
* **Zero-Hallucination:** Strictly grounded in uploaded PDF documents; refuses to guess.
* **Self-Learning Loop:** Escalated questions answered by humans are fed back into the vector database.
* **Safety Layer:** Filters out prompt injection, political discussions, and PII.

---

## 🛠️ Tech Stack & Prerequisites
To run this project, you need the following tools and accounts:

1.  **Orchestration:** [n8n](https://n8n.io/) (Self-hosted or Cloud).
2.  **Vector Database:** [Supabase](https://supabase.com/) (PostgreSQL + pgvector).
3.  **LLM:** OpenAI API (`gpt-4o-mini` for reasoning, `text-embedding-3-small` for embeddings).
4.  **Interface:** Telegram Bot Token (via @BotFather).
5.  **Escalation:** Google Cloud Console (Service Account for Sheets/Drive API).

---

## 🚀 Installation Guide

### Step 1: Clone the Repository
```bash
git clone [https://github.com/EzzNazzal/YGA-Training-Assistant.git](https://github.com/EzzNazzal/YGA-Training-Assistant.git)
cd YGA-Training-Assistant
