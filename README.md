# ⚡ SkillMatch AI: Resume Match & Skill Suggester

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-Framework-FF4B4B)
![AI](https://img.shields.io/badge/GenAI-Groq%20Llama--3-orange)
![NLP](https://img.shields.io/badge/NLP-BERT%20%7C%20NLTK-brightgreen)

**SkillMatch AI** is an intelligent, dual-purpose recruitment platform designed to bridge the gap between job seekers and recruiters. It utilizes advanced Natural Language Processing (BERT) to calculate semantic match scores and leverages Generative AI (Llama-3.3-70B) to dynamically restructure, rewrite, and format resumes into industry-standard ATS templates.

---

## 🚀 Key Features

### For Job Seekers
* **Smart Resume Parsing:** Upload existing resumes (PDF, DOCX, TXT) for instant data extraction.
* **Semantic JD Matching:** Get an accurate match score against target Job Descriptions using BERT embeddings and Cosine Similarity.
* **AI Grammar Coach:** Automatically rewrites weak bullet points into impactful, action-oriented professional statements.
* **Interactive Live Editor:** An intuitive Accordion UI to safely edit sections without infinite scrolling.
* **Real-Time Preview:** Visually accurately renders the final document in the browser.
* **Dynamic ATS Export:** One-click download of perfectly formatted Word (.docx) and PDF (.pdf) files in various templates (Executive, Modern Tech, Minimalist).

### For Recruiters
* **Campaign Management:** Create specific job campaigns.
* **Bulk Processing:** Upload multiple candidate resumes at once.
* **Automated Ranking:** Instantly rank candidates based on true semantic meaning rather than basic keyword matching.

---

## 🛠️ Tech Stack & Architecture

* **Frontend:** Streamlit (Python)
* **Backend:** Python 3
* **Database:** SQLite3 (Local, serverless storage with MD5 Hash checking to prevent duplicate API calls)
* **Natural Language Processing (NLP):** * `Sentence Transformers` (BERT) for dense mathematical vector embeddings.
  * `NLTK` for tokenization and stop-word removal.
* **Generative AI:** Groq API (Llama-3.3-70B-Versatile)
* **Document Processing:** * Parsing: `pdfplumber`, `python-docx`
  * Generation: `python-docx`, `fpdf2` (with automated text-wrapping)

---

## 📂 Project Structure

```text
├── core/
│   ├── nlp_engine.py       # BERT models and Cosine Similarity math
│   ├── llm_helper.py       # Groq API integration and prompt engineering
│   └── resume_parser.py    # PDF and DOCX text extraction
├── database/
│   └── db_queries.py       # SQLite transactions, auth, and hash-checking
├── pages/
│   ├── 1_JobSeeker.py      # Candidate dashboard, Live Editor, and exports
│   └── 2_Recruiter.py      # Recruiter campaign and bulk-ranking UI
├── utils/
│   └── report_generator.py # Dynamic PDF and DOCX styling logic
├── app.py                  # Main gateway, authentication, and routing
├── create_admin.py         # Utility to provision secure recruiter accounts
├── requirements.txt        # Project dependencies
└── .env                    # Secure environment variables (API Keys)