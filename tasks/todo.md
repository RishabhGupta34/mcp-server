# Task: Snippet/full command-unit log selection (stacked on #1575)

## Plan

- [x] `log-resolver`: snippet vs full mode; prefer failed units; reverse last-non-empty; labeled full sections; soft trim (no 8MB hard fail)
- [x] Wire `failedUnitNames` from `unitProgresses.status` through log-prefix / diagnose / harness-get
- [x] Cap unit keys from the **end** when over `MAX_COMMAND_UNIT_KEYS`
- [x] Update tests + `logs.ts` description
- [x] Push to `docs/logs-description-merge-units` (PR against Rishabh #1575)
- [x] Raise default `log_snippet_lines` / `DEFAULT_SNIPPET_LINES` from 120 → 200

## Done when

- Diagnose uses snippet mode (no merge-all-then-tail waste)
- Get uses labeled full mode
- Helm late-fail + early-fail cases covered by tests
- Default snippet tail is 200 lines
