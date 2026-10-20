# Resume Selector

Resume Selector compares PDF and DOCX resumes against the job description in `index.py` using the Groq API. It prints the top two and lowest two candidate matches.

## Requirements

- Python 3.11 or later
- [uv](https://docs.astral.sh/uv/)
- A Groq API key

## Setup

Clone the repository and install the project dependencies:

```powershell
git clone https://github.com/KonarkTyagi/AI-Resume-Screening-System.git
cd AI-Resume-Screening-System
uv sync
```

Create a `.env` file in the project root with your Groq API key:

```dotenv
GROQ_API_KEY=your_groq_api_key
```

Create the local resume folder and add the PDF or DOCX files you want to analyze:

```powershell
New-Item -ItemType Directory -Force src/resume_selector/resumes
```

The `.env` file and resume folder are excluded by `.gitignore`; they are not included in the repository.

## Run

From the project root, run:

```powershell
uv run python index.py
```

The script extracts text from each supported resume, sends it to Groq for analysis, and prints candidate match scores and details. Resume contents are sent to the Groq API, so only use documents you are authorized to process.
