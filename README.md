# TAILORAI

![Version](https://img.shields.io/badge/version-1.1.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Python](https://img.shields.io/badge/python-3.11%2B-blue.svg)
![Node](https://img.shields.io/badge/node-20%2B-blue.svg)

## Project Overview

**TAILORAI** is an Agentic AI Resume Customization System designed to rewrite and optimize LaTeX resumes for specific job descriptions. By leveraging LangChain and LangGraph, the system intelligently tailors resume content to align with job requirements while preserving factual accuracy and preventing AI hallucinations.

**Target Audience:** Job seekers, career coaches, recruiters, and developers building ATS-friendly resume optimization tools.

### Key Features

* **Smart Resume Tailoring** – Dynamically adapts Experience, Projects, Skills, and Education sections based on job descriptions.
* **Hallucination Prevention** – Prevents AI from inventing projects, metrics, employers, certifications, or skills.
* **Certification Protection** – Preserves the Certifications section exactly as provided.
* **Provider Agnostic Architecture** – Easily switch between OpenAI, Anthropic, Google Gemini, and Groq models.
* **LangGraph Workflow Orchestration** – Multi-step AI workflow for parsing, customization, validation, and generation.
* **Cover Letter Generation** – Creates role-specific cover letters using resume context and job descriptions.
* **LaTeX Validation** – Ensures valid and compilable LaTeX output.

---

## Tech Stack

### Backend

* FastAPI
* Python 3.11+
* LangChain
* LangGraph
* Pydantic
* YAML Configuration

### Frontend

* React
* Vite
* TypeScript

### AI & LLM Providers

* OpenAI
* Anthropic Claude
* Google Gemini
* Groq

### DevOps

* Docker
* Docker Compose

---

## Architecture

```text
Resume + Job Description
            │
            ▼
     Resume Parser
            │
            ▼
     LangGraph Workflow
            │
            ▼
  Section Customization
   ├── Experience
   ├── Projects
   ├── Skills
   └── Education
            │
            ▼
      LaTeX Validation
            │
            ▼
 Cover Letter Generation
            │
            ▼
      Final Output
```

---

## Prerequisites

Before installing the project, ensure you have:

* Python >= 3.11
* Node.js >= 20
* Docker (Optional)
* API Key from OpenAI, Anthropic, Google, or Groq

---

## Installation Instructions

### Option 1: Docker (Recommended)

1. Copy environment variables:

```bash
cp backend/.env.example backend/.env
```

2. Add your API key inside `backend/.env`.

3. Run:

```bash
docker compose up --build
```

---

### Option 2: Local Development

### Backend Setup

```bash
cd backend
cp .env.example .env
```

Add your API key inside `.env`.

Install dependencies:

```bash
uv sync
```

or

```bash
pip install -e .
```

Start backend:

```bash
uv run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```

---

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend:

```text
http://localhost:3000
```

Backend:

```text
http://localhost:8000
```

---

## Usage

### Web Interface

1. Paste your LaTeX Resume.
2. Enter Job Description.
3. Enter Target Role.
4. Select Cover Letter Generation (Optional).
5. Click **Forge Resume**.
6. Download or copy the generated content.

---

### API Example

```bash
curl -X POST http://localhost:8000/api/generate \
-H "Content-Type: application/json" \
-d '{
  "resume_latex":"\\begin{document}\\section{Experience}\\begin{itemize}\\item Built APIs\\end{itemize}\\end{document}",
  "job_description":"Looking for a backend engineer with API experience.",
  "role":"Backend Engineer",
  "generate_cover_letter":false
}'
```

---

## Configuration

### Model Configuration

Edit:

```text
backend/app/config/model_provider.yaml
```

Example:

```yaml
provider: openai
company: OpenAI
model: gpt-4o-mini
temperature: 0.2
```

Supported providers:

* openai
* anthropic
* google
* groq

### Environment Variables

Configure:

```env
OPENAI_API_KEY=
ANTHROPIC_API_KEY=
GOOGLE_API_KEY=
GROQ_API_KEY=
APP_PORT=
CORS_ORIGINS=
```

---

## Future Improvements

* ATS Score Calculator
* Resume Match Percentage
* PDF Export
* Resume History Tracking
* Authentication System
* Resume Analytics Dashboard
* Job Scraping Integration
* Resume Version Comparison
* One-Click LinkedIn Profile Optimizer

---

## Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Implement your changes.
4. Run formatting and validation checks.
5. Submit a Pull Request.

---

## License

This project is licensed under the MIT License.

---

## Author

**Rohan Swarnkar**

Computer Science Engineering Student

GitHub: https://github.com/ROHS9999

### Interests

* C++
* Python
* Data Structures & Algorithms
* AI / ML
* LLM Applications
* Backend Development
* Software Engineering
