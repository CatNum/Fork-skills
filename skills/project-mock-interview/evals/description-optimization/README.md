# Description optimization — run log

## 2026-05-18 run (partial)

- **Eval set**: `trigger-eval.json` (20 queries, 10 should-trigger / 10 should-not)
- **Tool**: `skill-creator` `run_loop.py` (model: sonnet, 3 runs/query, 40% holdout)
- **Iteration 1 baseline** (~15 min):
  - Train: **18/36** (accuracy 50%, precision 100%, **recall 0%**)
  - Test: **12/24** (same pattern)
  - **All should-trigger queries: 0/3** — severe undertrigger
  - **All should-not-trigger queries: passed** — no false positives
- **Stopped**: `improve_description` crashed (`claude -p exited 1`) before iteration 2

## Manual follow-up

`SKILL.md` description updated to imperative / pushy wording per skill-creator guidance (see git diff).

## Re-run (local)

```bash
cd ~/.agent/skills/skill-creator
PYTHONPATH=. python3 -m scripts.run_eval \
  --eval-set /path/to/Fork-skills/skills/project-mock-interview/evals/trigger-eval.json \
  --skill-path /path/to/Fork-skills/skills/project-mock-interview \
  --model sonnet --verbose --runs-per-query 3
```

Full loop:

```bash
PYTHONPATH=. python3 -m scripts.run_loop \
  --eval-set .../trigger-eval.json \
  --skill-path .../project-mock-interview \
  --model sonnet --max-iterations 5 --verbose \
  --results-dir .../description-optimization
```

Review queries: open `trigger-eval-review.html` in browser.
