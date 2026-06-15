# Decisions

## 2026-06-15: Assignment Automation Is A Standalone Repository

Decision: Use `O-right/chaoxing-assignment-automation` as the canonical GitHub repository and `D:\chaoxing_assignment_automation` as the active local clone for assignment-automation work.

Reason: The former combined workspace was split into workflow-specific repositories. Assignment automation has different dependencies, operational risks, and guardrails from course watching.

## 2026-06-15: Keep Runtime Secrets And Review Artifacts Out Of Git

Decision: Keep `.env`, logs, screenshots, review JSON files, browser profiles, cookies, tokens, credentials, API keys, and private assignment URLs untracked.

Reason: Live assignment experiments require private account and API configuration, but source control should contain only reusable automation code and public documentation.

## 2026-06-15: Real Submit Runs Require Guardrails

Decision: Keep manual reviewed-answer replay, confidence gates, unanswerable halts, selected-state verification, max-question cap checks, low-score/retry halts, and high-risk review behavior as the default experiment stance.

Reason: Earlier real assignment experiments exposed risks from model uncertainty, malformed extraction, non-persisted clicks, hidden text control ordering, and same-URL result pages. Halting is preferred over submitting weak or unverifiable state.

## 2026-06-15: Restore Safer Defaults After Experiment Phase

Decision: The current real-site hard-block relaxation is temporary. Before normal operation, restore safe defaults that prevent live AI/action/submit behavior on real academic assignment hosts unless explicitly authorized.

Reason: The assignment module is high-risk and should default to dry-run or controlled fixtures outside the temporary experiment phase.
