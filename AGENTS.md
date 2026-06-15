# Project Agent Rules

## Project Context

- This repository is the standalone Chaoxing assignment automation project.
- The workflow logs in, scans Chaoxing Inbox notices, resolves assignment attachments, extracts questions, runs guarded AI-assisted answer experiments, and handles manual-review replay and submit/result paths.
- Assignment automation is operationally higher risk than course watching. Keep runs authorized, bounded, and guardrailed.

## Commands

- Install dependencies: `python -m pip install -r requirements.txt`
- Install browser: `python -m playwright install chromium`
- Run monitor/automation: `python assignment_tester.py`
- Syntax check: `python -m py_compile assignment_tester.py`

## MUST DO

- Read `docs/STATUS.md`, `docs/TASKS.md`, `docs/ARCHITECTURE.md`, `docs/DECISIONS.md`, and `docs/PRD.md` before non-trivial changes.
- Keep URLs, credentials, selectors, AI endpoint settings, review controls, browser options, and safety gates configurable through `.env` or environment variables.
- Keep manual-review, confidence, unanswerable, selected-state, question-cap, low-score, and retry-marker guardrails intact unless the user explicitly changes the experiment stance.
- Prefer local fixtures and dry-run evidence before live assignment experiments.

## MUST NEVER

- Never commit real passwords, API keys, tokens, cookies, private assignment URLs, `.env`, logs, review files, screenshots, or browser profiles.
- Never bypass access controls, payment controls, CAPTCHA, MFA, SMS login, or site terms.
- Never claim an assignment was submitted or scored unless the exact configured run produced that result.
