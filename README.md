# YGA Training Assistant (HTU) 🎓🤖

**Developer:** EzzEdden Nazzal  
**Program:** Generative AI Training (HTU)  
**Date:** February 7, 2026

![Project Status](https://img.shields.io/badge/Status-Completed-success) ![Tech Stack](https://img.shields.io/badge/Stack-n8n%20|%20Supabase%20|%20OpenAI-blue)

## 📄 Overview
The **YGA Training Assistant** is a multi-channel AI system designed to automate Tier-1 support for the Youth Grow Activity (YGA) training program at Al Hussein Technical University (HTU).

The program supports hundreds of students across four technical tracks: QA, DevOps, Gen AI, and UI/UX. This system alleviates the operational bottleneck for the Project Coordinator (Ms. Zain) by automating repetitive inquiries regarding admissions, schedules, and attendance policies.

## 🏗️ System Architecture
The architecture is built on a **Low-Code** stack using n8n for orchestration:
* **Input Layer:** Telegram API Webhook & Custom Web Widget.
* **Safety Layer:** Pre-processing nodes to filter "Out of Scope" and "Injection" attacks.
* **Retrieval Layer:** Supabase (pgvector) stores the knowledge base chunks.
* **Model Layer:** OpenAI (Embeddings) + GPT-5-mini (Reasoning/Generation).
* **Escalation Layer:** Google Sheets acts as the "Human-in-the-Loop" interface.

## ⚡ Key Features
1.  **Multi-Channel Support:** Accessible via Web (HTML5 formatted) and Telegram (Text).
2.  **RAG Architecture:** Strictly grounded in retrieved documents to prevent hallucination.
3.  **Self-Learning Loop:** Unanswered questions are logged to Google Sheets. Once approved by the admin, they are automatically embedded back into the vector store.
4.  **Optimized Retrieval:** Uses Cohere Reranker to boost retrieval accuracy by re-ordering documents based on semantic relevance.

## 🚀 Setup & Installation
1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/EzzNazzal/YGA-Training-Assistant.git](https://github.com/EzzNazzal/YGA-Training-Assistant.git)
    ```
2.  **Import Workflows:**
    * Navigate to your n8n dashboard.
    * Import the `.json` files located in `src/workflows/`.
3.  **Environment Variables:**
    * Set up your credentials for `OPENAI_API_KEY`, `SUPABASE_URL`, `TELEGRAM_BOT_TOKEN`, and `COHERE_API_KEY`.
4.  **Database Setup:**
    * Run the SQL scripts in `src/database/schema.sql` to enable the `pgvector` extension in Supabase.

## 📊 Evaluation
The system was evaluated using a "Golden Dataset" of 20 FAQ pairs not included in the training data.
* **Response Faithfulness:** 96%
* **Model Selection:** GPT-5-mini was chosen for its sub-0.8s latency and superior reasoning capabilities compared to GPT-4o-mini.

---
*For a detailed breakdown of the logic and failure analysis, please refer to the [Technical Report](docs/technical_report.pdf).*
