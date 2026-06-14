# Chaoxing Assignment Automation

This folder is the split-out assignment automation project. The automation logic is copied unchanged from the root `assignment_tester.py`.

## Setup

```powershell
python -m pip install -r requirements.txt
python -m playwright install chromium
```

## Run

```powershell
python assignment_tester.py
```

Useful checks:

```powershell
python -m py_compile assignment_tester.py
```

The runner reads assignment configuration from local `.env` or process environment variables such as `ASSIGNMENT_INBOX_URL`, `ASSIGNMENT_AI_API_URL`, `ASSIGNMENT_AI_API_KEY`, and `ASSIGNMENT_AI_MODEL`.

Keep runs authorized and bounded. Do not commit `.env`, logs, review files, cookies, tokens, passwords, or API keys.
