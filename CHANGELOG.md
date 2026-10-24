# Change log

## 2026-10-25T00:14:40+05:30 — Harden meeting transcription and browser companion

- Changed: imported the current LocalFlow meeting and extension updates, including participant roster replay, socket/tab lifecycle handling, speaker-attribution safeguards, meeting-specific model routing, stop/finalization fixes, and regression coverage. See `MEETING_AUDIT.md` for details and remaining risks.
- Why: address lost participant state, stale meeting data, incomplete transcription tails, and summary/model routing errors.
- Validation: `go test ./...` passed; `node --test extension/bridge.test.cjs` passed 7/7; `npm run build` passed with Vite warnings about Wails runtime scripts and an unresolved Urbanist font. `npm ci` reported 5 dependency audit findings (1 moderate, 4 high). Live browser-call validation remains pending.
- Limitations: platform DOM selectors and speaker attribution remain unverified in live calls; the local WebSocket bridge has no pairing token. Human review is pending.

## 2026-10-25T00:10:21+05:30 — Bring LocalFlow into the Devin Hack Kochi repository

- Changed: merged the existing template repository history with LocalFlow's original Git history; adapted this README and combined template and project ignore rules.
- Why: use the event template as the project repository while retaining both histories and the existing template guidance.
- Validation: retained the template and LocalFlow histories and source tree. `git diff --cached --check` reported existing whitespace in imported source files; application checks are pending.
- Limitations: the source working-tree updates are to be recorded in a follow-up commit; team and demo details remain TODO; application checks are pending.

## 2026-10-24T21:53:05+05:30 — Correct Devin Hack Kochi event guidance

- Changed: corrected the current event name and AI tool guidance in `.github/pull_request_template.md`, `AGENTS.md`, `AI_USAGE.md`, `CHANGELOG.md`, `README.md`, `RULES.md`, `SUBMISSION.md`.
- Why: the organizer shared an older event template; Devin Hack Kochi has no
  major AI usage constraints and the template must not require a particular AI provider.
- Scope: preserved project implementation and historical assistance records.
- Removed obsolete template logistics, participation limits, and credit promises; current organizer instructions remain authoritative.
- Validation: reviewed documentation diffs, checked whitespace with `git diff --check`, and checked local Markdown links for new breakage.
- Limitations: maintainer review is pending; application tests were not run for this documentation-only correction.

Record each meaningful project change during the event, newest first. Update this file in the same commit as the change. Use a real timestamp with timezone, for example `YYYY-MM-DDTHH:MM:SS+05:30`.

## Event build log

No project implementation has been recorded yet. Replace this sentence with entries as you build:

```text
## <actual timestamp> — <short change title>

- Changed: <feature or files changed>
- Why: <reason for the change>
- Validation: <commands or manual checks actually run, with results>
- Limitations: <known issues or "None identified in these checks">
```

## Template setup — 10 October 2026

- Changed: Added the event README, rules, agent guide, change log, AI usage record, submission checklist, Git ignore rules, and pull request checklist.
- Why: Give participants a consistent starting point for event rules, basic coding patterns, documented changes, and regular commits.
- Validation: Checked local Markdown links, event detail consistency, required documents, and diff whitespace before publishing.
- Limitations: Documentation scaffolding only; no participant project, application, or working demo is included. GitHub publication and template status are verified separately after creation.
