# PRD: Chaoxing Assignment Automation

## Goal

Maintain a Python + Playwright assignment automation that can monitor authorized Chaoxing Inbox assignment notices, resolve assignment pages, extract question state, run guarded AI-assisted answer experiments, and stop or submit according to the current safety configuration.

## Requirements

- Load login, Inbox, selector, AI endpoint, browser, review, and safety settings from `.env` and `ASSIGNMENT_*` environment variables.
- Navigate through Chaoxing Inbox rather than course fallback pages.
- Detect assignment notices whose titles contain `作业:` or `作业：`.
- Resolve notice attachments to real assignment pages.
- Extract question text, options, question type, controls, shared-option groups, text/fill-in controls, UEditor-backed controls, and media screenshots where needed.
- Normalize AI responses into browser-actionable answers.
- Verify answer state after clicks or fills before treating a question as completed.
- Stop on low confidence, unanswerable questions, high-risk review disagreement, malformed extraction, question-cap overflow, low score, or retry markers.
- Require manual reviewed-answer replay before real submit-enabled experiment runs by default.
- Handle Chaoxing submit buttons, native dialogs, custom confirmation layers, and same-URL result pages.

## Safety And Policy Boundaries

- Runs must be authorized and bounded.
- Do not bypass access controls, payment controls, CAPTCHA, MFA, SMS login, or site terms.
- Never commit, print, or document real passwords, cookies, API keys, access tokens, private URLs, `.env`, logs, review files, or screenshots.
- The current real-site hard-block relaxation is temporary experiment state. Restore safer defaults before normal operation.

## Acceptance Criteria

- `python -m py_compile assignment_tester.py` passes.
- Local fixtures or dry-runs validate extraction/action changes before live use.
- Real submit-enabled runs require reviewed-answer replay unless explicitly changed.
- Result or score claims are backed by exact run evidence.
- Runtime artifacts stay ignored and untracked.

## Out Of Scope

- CAPTCHA solving.
- MFA or SMS automation.
- Scraping unrelated private data.
- Circumventing access controls or site restrictions.
- CI against a private live Chaoxing assignment.
