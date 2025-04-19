# 🤖 AI Agent with Google ADK

An intelligent AI agent built using [Google ADK (Agent Development Kit)](https://google.github.io/adk-docs/).  
This agent can answer user queries, analyze uploaded images, and is planned to support voice and video input in future updates.

---

## 📦 Project Overview

This project serves as a base for building multimodal AI-powered applications using Gemini models from Google, with modular and extendable functionality such as:

- Time and weather queries
- Image understanding
- Future support: voice streaming, video analysis

---

## 📁 Project Structure

```
google-adk-test/
├── .gitignore
├── README.md
├── multi_tool_agent/
│   ├── __init__.py
│   ├── agent.py
│   └── .env
└── .venv/
```

---

## 🚀 Features

- ✅ Text-based interaction (weather & time)
- ✅ Image understanding (image → text)
- 🔜 Voice streaming support (via Gemini Live API)
- 🔜 Video input analysis
- 🔄 Easily add custom tools/functions

---

## 🛠️ Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/ikhwan-fauzi/google-adk-test.git
cd google-adk-test
```

### 2. Create and Activate a Virtual Environment

```bash
python -m venv .venv

# Activate the environment:
# On Windows:
.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install google-adk
```

> Or, if using `requirements.txt`:

```bash
pip install -r requirements.txt
```

### 4. Set Up Folder and Files

```bash
mkdir multi_tool_agent
echo "from . import agent" > multi_tool_agent/__init__.py
```

### 5. Configure Environment Variables

Create a `.env` file inside `multi_tool_agent/` with the following content:

```
GOOGLE_API_KEY=your_gemini_api_key_here
MODEL=gemini-2.0-pro
```

> You can use Gemini from either [Google AI Studio](https://makersuite.google.com/app) or [Vertex AI](https://console.cloud.google.com/vertex-ai/).

---

## 🧠 How It Works

The `agent.py` file defines a simple agent with two tools:

- `get_weather(city: str)`  
  → Returns a dummy weather report for “New York” or an error for other cities.

- `get_current_time(city: str)`  
  → Returns the current time for “New York”.

You can register more functions (tools) and pass them into the `Agent` object to extend its abilities.

---

## 💡 Running the App

Run the web UI to interact with your agent:

```bash
adk web
```

> If `adk` is not recognized, try:

```bash
python -m google.adk.cli web
```

---

## 🧪 Technologies Used

- Python 3.10+
- Google ADK
- Gemini API (via Google AI)
- FastAPI (provided by ADK)
- Uvicorn (for local dev server)
- dotenv (for env vars)
- Pydantic
