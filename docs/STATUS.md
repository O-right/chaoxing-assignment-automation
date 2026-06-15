# Status

## Current Phase

Standalone assignment-automation repository created and synced from the former combined workspace.

## Current Focus

This repository now contains only the assignment automation workflow. The active local clone is `D:\chaoxing_assignment_automation`, tracking `git@github.com:O-right/chaoxing-assignment-automation.git`. The old combined workspace at `D:\course_rpa_node` should be treated as a handoff/archive location, not the normal place for assignment-automation commits.

## Recent Evidence

- The split repository clone was created locally at `D:\chaoxing_assignment_automation`.
- `python -m py_compile assignment_tester.py` passed in this standalone clone.
- `git diff --check` passed after adding handoff docs.
- Local `.env` was copied from the former combined workspace and is ignored by Git.
- Local Git status was clean before adding these handoff docs.
- Earlier combined-workspace evidence showed Inbox scanning, question extraction, image payload construction, confidence gating, selected-state verification, manual review replay, and same-URL result detection working in targeted checks.

## Next Steps

- Use this repository for future assignment-automation changes and commits.
- Keep local `.env` outside Git; recreate it only if the file is deleted or credentials change.
- Run local fixture or dry-run checks before any live assignment experiment.
- Restore safer defaults and real-site hard-blocking when the temporary experiment phase ends.

## Blockers And Cautions

- `.env` exists locally for this clone but is intentionally ignored and must not be committed or printed.
- AI backend health is an external prerequisite for live AI experiments.
- Confidence and review guardrails reduce risk but are not correctness proof.
- Do not claim a submit or score unless the exact run produced it.

## Active Files

- `assignment_tester.py`
- `requirements.txt`
- `README.md`
- `AGENTS.md`
- `docs/`
