# Tasks

## Setup

- [x] Create standalone GitHub repository `O-right/chaoxing-assignment-automation`.
- [x] Clone standalone local repository at `D:\chaoxing_assignment_automation`.
- [x] Include `assignment_tester.py`, `requirements.txt`, `.gitignore`, and README.
- [x] Add project handoff docs and repo rules.

## Validation

- [x] Verify repository tracks `git@github.com:O-right/chaoxing-assignment-automation.git`.
- [x] Verify local branch tracks `origin/main`.
- [x] Run `python -m py_compile assignment_tester.py`.
- [ ] Run local fixture or dry-run checks before the next behavior change.
- [ ] Run a bounded live Inbox scan only when credentials, AI backend, and authorization are available.

## Future Work

- [ ] Restore assignment tester safe defaults and real-site hard-block after the temporary experiment phase.
- [ ] Add focused local regression fixtures for future extraction or submit-flow fixes.
- [ ] Add structured logging if long-run diagnostics need cleaner output.
