# 🐍 Python Tutor AI — Your Personal Python Teacher

A modern, full-stack, AI-powered interactive learning platform designed for college students and beginners learning Python programming.

---

## 🌟 Key Features

1. **🤖 Interactive AI Tutor Chat:**
   - Ask Python questions in simple natural language.
   - Tailored learning levels: **Beginner**, **Intermediate**, and **Advanced**.
   - **Marathi Explanations Mode:** Learn Python concepts explained in simple Marathi with English programming terms.
   - Includes real-world analogies, syntax breakdowns, and practice challenges.

2. **📖 12-Module Structured Curriculum:**
   - Complete learning roadmap covering:
     1. Introduction to Python
     2. Variables & Data Types
     3. Operators & Expressions
     4. Conditional Statements
     5. For Loops & While Loops
     6. Strings & Text Processing
     7. Collections (Lists, Tuples, Sets, Dictionaries)
     8. Functions & Scope
     9. Object-Oriented Programming (OOP)
     10. File Handling
     11. Exception Handling
     12. Beginner Projects

3. **💻 Code Generator & Playground:**
   - Monaco Editor with syntax highlighting.
   - Prompt-driven AI code generator (e.g. *"Write a program to check prime numbers"*).
   - Generates problem logic, algorithm steps, source code, line-by-line explanations, and time/space complexity.

4. **🔒 Safe Python Execution Sandbox:**
   - Run Python code directly in a safe, isolated subprocess sandbox.
   - Restricts unsafe operations (`os`, `sys`, `subprocess`, `open`) and prevents infinite loops with a 4.0-second timeout.
   - Captures console output and execution time.

5. **🐛 AI Code Debugger:**
   - Paste broken Python code and error stack traces.
   - Analyzes syntax, runtime, and logical errors.
   - Returns corrected code, line-by-line explanations, and edge-case warnings.

6. **🎯 Practice & MCQ Quiz System:**
   - Generates multiple-choice questions by skill level.
   - Instant feedback, hints, answer explanations, and score tracking.

7. **🗺️ Roadmap & Progress Dashboard:**
   - Tracks completed curriculum modules and quiz scores locally in browser `localStorage`.

---

## 🛠️ Technology Stack

- **Frontend:** React, Vite, Lucide Icons, Monaco Editor (`@monaco-editor/react`), Vanilla CSS design system (pastel blue, white, and soft lavender theme).
- **Backend:** Python 3.14, FastAPI, Uvicorn, Pydantic, HTTPX, `python-dotenv`, `google-genai`.
- **AI Integration:** Google Gemini API (or OpenAI/fallback smart offline tutor when key is not set).

---

## 🚀 Setup & Execution Instructions (Windows PowerShell / VS Code)

### Prerequisites
- **Python 3.10+** (Python 3.14 installed)
- **Node.js v18+** (Node v24 installed)

---

### Step 1: Clone or Open Workspace
Open VS Code terminal in your project folder:
```powershell
cd "c:\Users\Raj\OneDrive\Desktop\python AI agent"
```

---

### Step 2: Configure Environment Variables (.env)
1. Copy `.env.example` to create your private `.env` file:
```powershell
Copy-Item .env.example .env
```
2. Open `.env` and add your free Google Gemini API Key:
```env
GEMINI_API_KEY=AIzaSyYourActualKeyHere
```
*(Get a free API key from [Google AI Studio](https://aistudio.google.com/app/apikey))*

> ⚠️ **Note:** If no API key is set, the application will run seamlessly in **Smart Demo Mode** with pre-built educational Python explanations!

---

### Step 3: Run the FastAPI Backend Server

1. Open a terminal tab and navigate to the backend:
```powershell
python -m uvicorn app.main:app --host 127.0.0.1 --port 8000 --reload
```
2. Verify backend is running by opening: `http://127.0.0.1:8000/api/health`

---

### Step 4: Run the React Frontend Application

1. Open a **second** terminal tab and navigate to the frontend:
```powershell
cd frontend
npm run dev
```
2. Open your browser at the URL shown in the terminal (usually `http://localhost:5173`).

---

## 🧪 Testing the Application

To run automated backend endpoint verification:
```powershell
python -c "import httpx; print(httpx.get('http://127.0.0.1:8000/api/health').json())"
```

To test safe code execution:
```powershell
python -c "import httpx; print(httpx.post('http://127.0.0.1:8000/api/run-code', json={'code': 'print(\"Hello Python!\")'}).json())"
```

---

## 🔐 Security Safeguards

- **API Key Privacy:** All API keys are kept strictly on the backend server (`.env`) and never exposed to client-side JavaScript.
- **Sandbox Security:** User-submitted Python code is executed in an isolated process with AST security checks, restricted builtins, and strict execution timeouts.

---

## 📄 License
MIT License. Built for interactive Python education.
