# Chapter 2: Blood Work Analyzer

An AI-powered medical report analysis and diet planning application. This project uses a two-stage LLM pipeline (built with LangChain and Google GenAI) to analyze blood test reports, flag out-of-range values, and generate personalized health summaries and practical Indian diet recommendations.

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](YOUR_DEPLOYED_URL_HERE)

**[🔗 Live Demo](YOUR_DEPLOYED_URL_HERE)**

---

## Features

- **Two-Stage Analysis Pipeline**:
  - **Stage 1 (Extraction & Classification)**: Parses unstructured blood report text, extracts test names with their values, and compares them against reference ranges to flag them as `HIGH`, `LOW`, or `NORMAL`.
  - **Stage 2 (Actionable Advice)**: Translates technical metrics into a simple layperson summary and produces a localized Indian diet plan (Foods to Eat / Foods to Avoid).
- **Interactive Streamlit Web Dashboard**: A user-friendly web interface that presents side-by-side analysis, complete with scrollable response widgets and responsive styling.
- **Jupyter Notebook Prototype**: A step-by-step notebook outlining the underlying LLM pipeline design.

---

## File Structure

The project directory is structured as follows:

```text
2_health_analysis/
├── README.md                   # This documentation
├── blood_work.txt              # Sample unstructured blood test report
├── blood_work_analysis.ipynb   # Jupyter Notebook containing the pipeline prototype
└── streamlit_app/
    └── app.py                  # Streamlit application source code
```

---

## Setup & Running Guide

### 1. Prerequisites
Ensure you have completed the root setup and have the project environment installed.
This chapter requires the package dependencies (like `streamlit` and `langchain-google-genai`) to be installed in your environment. If they are not already installed, run from the root folder:
```bash
python3 -m pip install -e .
```

### 2. Configure API Keys
Make sure you have created the `.env` file in the root directory:
```bash
cp ../.env.sample ../.env
```
Open [`.env`](../.env) and add your Gemini Developer API Key:
```env
GOOGLE_API_KEY=your_actual_gemini_api_key_here
```

### 3. Run the Streamlit App
Navigate to the `2_health_analysis` folder and start the web dashboard:
```bash
streamlit run streamlit_app/app.py
```
This will start a local server, usually opening at `http://localhost:8501` or `http://localhost:8502`.

### 4. Run the Jupyter Notebook Prototype
To explore or modify the raw pipeline code:
1. Start the notebook server:
   ```bash
   jupyter notebook
   ```
2. Open and run [`blood_work_analysis.ipynb`](blood_work_analysis.ipynb).
