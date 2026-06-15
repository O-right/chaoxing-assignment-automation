# Architecture

## System Shape

This repository is a single-workflow Python + Playwright project for Chaoxing assignment monitoring and guarded interaction experiments. It is one of two split repositories created from the former combined workspace.

## Components

- `assignment_tester.py`
  - Main assignment automation entrypoint.
  - Handles login, Inbox scanning, notice detail navigation, attachment resolution, question extraction, AI calls, answer normalization, guarded browser actions, review-file replay, submit confirmation, and result detection.
- `requirements.txt`
  - Declares Playwright, `python-dotenv`, and `requests`.
- `docs/`
  - Current status, tasks, architecture, decisions, and product scope for handoff.

## Runtime Flow

1. Build configuration from `.env` and `ASSIGNMENT_*` environment variables.
2. Launch Playwright and log in to Chaoxing.
3. Navigate to the configured Inbox shell or direct Inbox URL.
4. Scan `li.dataBody_item > a.notice_title` notices for assignment keywords.
5. Open notice details through `.openNotice[data-url]`.
6. Resolve the real assignment page from attachment iframe globals such as `window.att_web.url` or `window.screenOpenUrl`.
7. Extract all supported question containers and controls.
8. Request structured AI answers only when allowed by configuration.
9. Normalize answers and apply them through guarded click/fill paths.
10. Verify selected or filled state after each action.
11. Halt on configured risk conditions, or require reviewed-answer replay before submit.
12. Handle submit confirmation and same-URL result pages.

## Guardrails

- Manual pre-submit review is required by default for real submit-enabled experiment runs.
- Low-confidence, unanswerable, high-risk disagreement, malformed extraction, max-question cap, selected-state failure, low score, and retry markers must halt the run.
- The current real-site hard-block relaxation is temporary and should be restored before normal operation.

## Configuration And Secrets

- Local `.env` and runtime environment variables hold private configuration.
- `.env`, logs, review files, screenshots, browser profiles, cookies, tokens, API keys, and private URLs must remain untracked.
- This repository's remote is `git@github.com:O-right/chaoxing-assignment-automation.git`.

## Validation

- Baseline: `python -m py_compile assignment_tester.py`.
- Prefer local Playwright fixtures and dry-runs for extraction, mapping, and submit-confirmation changes.
- Live runs must be authorized, bounded, and documented with exact evidence before claims are made.
