---
name: add-japanese-localization-with-html-viewers
description: Workflow command scaffold for add-japanese-localization-with-html-viewers in ralph-orchestrator.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-japanese-localization-with-html-viewers

Use this workflow when working on **add-japanese-localization-with-html-viewers** in `ralph-orchestrator`.

## Goal

Adds Japanese localization for documentation and examples by creating parallel .ja.md files and generating interactive .ja.html viewer files, while updating or refining localization tooling/scripts.

## Common Files

- `*.ja.md`
- `*.ja.html`
- `scripts/build_ja_viewers.py`
- `scripts/check_ja_coverage.py`
- `scripts/ja_scope.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or translate .ja.md files for each documentation or example file.
- Generate corresponding .ja.html viewer files using build scripts.
- Update or refine localization scripts (e.g., coverage checker, viewer builder).

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.