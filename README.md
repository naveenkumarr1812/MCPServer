# Project Setup Guide

This guide will help you set up and run the Learn_MCP project, which demonstrates using a Model Context Protocol (MCP) math server with LangChain.

## Prerequisites
- Python 3.8 or higher (recommended: use a virtual environment)
- [uv](https://github.com/astral-sh/uv) (a fast Python package manager)
- A valid GROQ API key (for ChatGroq)

## 1. Clone the Repository
```
git clone <your-repo-url>
cd mathServer-FastMCP
```

## 2. Create and Activate a Virtual Environment (optional but recommended)
```
python -m venv .venv
# On Windows:
.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate
```

## 3. Install Dependencies with uv
```
uv pip install -r requirements.txt
```
Or, to use the lockfile (if present):
```
uv pip sync uv.lock
```

## 4. Set Up Environment Variables
Create a `.env` file in the project root with your GROQ API key:
```
GROQ_API_KEY=your_groq_api_key_here
```

## 5. Run the Math Server
The math server will be started automatically by the client script as a subprocess (`mathserver.py`). You do not need to start it manually.

## 6. Run the Client
```
uv pip run python client.py
```
Or simply:
```
python client.py
```

## 7. Troubleshooting
- If you see `ImportError: langchain_mcp_adapters.fastapi could not be resolved`, ensure the package is installed or available in your environment.
- If you get errors about missing modules, check your `requirements.txt` and install any missing dependencies.
- Make sure your `.env` file is present and contains a valid `GROQ_API_KEY`.

## 8. Project Structure
- `client.py` — Main client that connects to the math MCP server
- `mathserver.py` — Math MCP server (started by the client)
- `requirements.txt` — Python dependencies
- `.env` — Environment variables (not committed to version control)

---

Feel free to update this README with additional details as your project evolves.
