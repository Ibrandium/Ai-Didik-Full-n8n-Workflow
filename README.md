# 🚀 AI-Didik: Intelligent Automation for Educators

**AI-Didik** is a suite of low-code automation workflows designed to reduce the administrative burden on teachers. Built using **n8n**, this project leverages Generative AI (LLMs) and Vector Databases (RAG) to automate exam creation, student reporting, daily classroom feedback analysis, and curriculum research.

---

## 📂 The Workflows

This repository contains four core automation modules:

### 1. 📝 AI Exam Paper Generator (Sejarah Tingkatan 4)
*Located in: `/AI-Exam-Generator`*

**The Problem:** Creating KPM-standard History exams takes hours of manual formatting and question drafting.
**The Solution:**
* **Input:** Fetches raw textbook content stored in **Supabase**.
* **Processing:** Uses **OpenAI (GPT-4o)** to generate Objective, Structural, and Essay questions based on the input chapter.
* **Output:** Automatically splits content into a **Question Paper** and an **Answer Schema**, saving both as separate Google Docs.

### 2. 📊 Student Portfolio & Report Card System
*Located in: `/Student-Portfolio`*

**The Problem:** Manually updating slide decks for parent-teacher meetings is repetitive and prone to error.
**The Solution:**
* **Input:** Pulls student grades, behavior scores, and co-curricular data from **NocoDB**.
* **Processing:** An AI Agent analyzes the data to write a personalized "Scientific Comment" for each student (identifying weak subjects and suggesting physiological/habit changes).
* **Output:** Auto-fills a **Google Slides** template with the data and AI comments, creating a presentation ready for the classroom.

### 3. 🗣️ AI Exit Ticket Analyzer (Telegram Bot)
*Located in: `/AI-Exit-Ticket-Analyzer`*

**The Problem:** Teachers struggle to analyze 30+ exit tickets daily to adjust lesson plans for the next day.
**The Solution:**
* **Input:** Collects daily student feedback via **Google Forms/Sheets**.
* **Trigger:** A Cron job triggers the workflow daily at 4 PM.
* **Processing:** AI analyzes the bulk responses to find common misconceptions and learning gaps.
* **Output:** Sends a concise summary and specific teaching recommendations directly to the teacher via **Telegram**.

### 4. 🇲🇾 Sarawak Research Assistant (RAG)
*Located in: `/Sarawak-Research-Assistant`*

**The Problem:** Teachers lack localized resources to connect standard curriculum with Sarawak's specific history and geography.
**The Solution:**
* **Trigger:** Telegram command `/findlocal [topic]`.
* **Processing:** Uses **RAG (Retrieval-Augmented Generation)**. It searches a vector database (Supabase) containing scanned History textbooks to find relevant local facts.
* **Memory:** Uses **Postgres** to remember previous chat context for the teacher.
* **Output:** Generates a structured lesson guide (Facts, Teaching Ideas, Student Activities) based on the local context.

---

## 🛠️ Tech Stack

* **Orchestration:** [n8n](https://n8n.io/)
* **Database:** Supabase (Vector Store), NocoDB, Google Sheets, Postgres
* **AI Models:** OpenAI (GPT-4o / GPT-4o-mini)
* **Storage & Docs:** Google Drive, Google Slides, Google Docs
* **Interface:** Telegram Bot API

---

## ⚡ How to Use

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/Ibrandium/Ai-Didik-Full-n8n-Workflow.git](https://github.com/Ibrandium/Ai-Didik-Full-n8n-Workflow.git)
    ```

2.  **Import to n8n:**
    * Open your n8n instance.
    * Select "Import Workflow" and choose the `.json` file from the specific project folder.

3.  **Setup Credentials:**
    * You will need API keys for: **OpenAI, Supabase, Telegram, and Google Cloud Console (Drive/Sheets/Slides)**.
    * *Note:* Sample data (CSVs) and Templates (PPTX) are provided in the respective folders for testing.

---

**Project maintained by Ibrandium.**
*Automating Education, One Workflow at a Time.*
