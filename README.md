# GLR Insurance Automation Pipeline  
### **AI-Powered Template Filling (Streamlit + OpenRouter + GPT-4o-mini)**

This project automatically fills GLR templates using multiple PDF photo reports and an LLM-driven semantic extraction pipeline. It supports multiple extraction modes (High-Accuracy, Strict Validation, Field Audit, Multi-LLM Voting) and produces a fully completed `.docx` output file with near-zero missing fields.

---

## Features

- Upload a `.docx` GLR template with placeholders like `[INSURED_NAME]`
- Upload one or more PDF photo reports (text-based)
- Automatically extract and interpret insurance-specific fields using LLMs
- 4 AI extraction engines:
  - **High Accuracy Mode** — multi-step reasoning + confidence scoring
  - **Strict Validation Mode** — VERIFIED/INFERRED/MISSING classification
  - **Field Audit Mode** — value + one-sentence evidence
  - **Multi-LLM Voting Mode** — consensus from multiple inference passes
- Deterministic fallback heuristics for guaranteed completeness
- Generate a final **fully-filled `.docx` file**
- Clean Streamlit web interface

---

## AI Extraction Modes

| Mode | Description | Best For |
|------|-------------|----------|
| **High Accuracy** | Multi-step reasoning + confidence rating | Highest field quality |
| **Strict Validation** | VERIFIED / INFERRED / MISSING + evidence | Compliance, audit logs |
| **Field Audit** | Each value has 1-sentence evidence | Transparency |
| **Multi-LLM Voting** | Multiple inference rounds → majority vote | Ambiguous PDFs |

---

## Tech Stack

- **Python 3.10+**
- **Streamlit**
- **OpenRouter API** (GPT-4o-mini)
- **pdfplumber**
- **python-docx**
- **Regex-based fallback extraction**

---

## Installation

```bash
git clone https://github.com/YOUR_USERNAME/glr-automation-pipeline.git
cd glr-automation-pipeline
pip install -r requirements.txt
```

---

## Environment Variables

Create a `.env` file:

```
OPENROUTER_API_KEY=your_api_key_here
```

---

## Run the App

```
streamlit run app.py
```

---

## Output

After processing, the app will generate:

```
Filled_GL_Report_YYYYMMDD_HHMMSS.docx
```

containing **all placeholders filled** with validated data.

