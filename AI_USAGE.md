# AI usage record

If maintaining this record, briefly document the actual contributions of whichever AI tools you use at Devin Hack Kochi. Add a row after each meaningful task or milestone. Keep summaries concise and omit secrets, private data, and full chat transcripts.

## Event build log

This log records actual AI assistance on the project; human review remains pending until a participant reviews each contribution.

| Date and time with timezone | Tool / model, if known | Task | Assistance and affected files | Human review / corrections | Validation and result |
| --- | --- | --- | --- | --- | --- |
| 2026-10-25T00:18:27+05:30 | OpenAI Codex (GPT-6) | Clarify Windows validation setup | Updated README.md and CHANGELOG.md with the native DLL PATH requirement | Pending | Matched instructions to the passing local Go test command |
| 2026-10-25T00:17:26+05:30 | OpenAI Codex (GPT-6) | Record the pushed implementation revision | Updated SUBMISSION.md and CHANGELOG.md with the current pushed SHA | Pending | Confirmed de300ea5162946d9ca4540c8bde90ea7058a9767 is present on pushed main |
| 2026-10-25T00:14:40+05:30 | OpenAI Codex (GPT-6) | Integrate LocalFlow into the Devin Hack Kochi template and document current meeting fixes | Inspected both histories; merged them; adapted `.gitignore`, `README.md`, `CHANGELOG.md`, and `SUBMISSION.md`; imported meeting/extension backend and frontend changes plus regression checks | Pending | `go test ./...` passed; extension tests passed 7/7; frontend build passed with warnings; npm reported 5 audit findings; live browser validation pending |

## Template preparation

This historical preparation note refers to the older template. It does not define Devin Hack Kochi's event rules or AI tool requirements.

On 10 October 2026, Codex prepared this documentation template from the organizer's supplied rules and checked the linked Luma page for the event name and dates. This covered `README.md`, `RULES.md`, `AGENTS.md`, `CHANGELOG.md`, `AI_USAGE.md`, `SUBMISSION.md`, `.gitignore`, and the pull request checklist. Agent validation covered local links, event consistency, required documents, and diff whitespace; organizer review is pending.

This preparation is separate from participant project implementation and participant AI usage during the event.

## Event documentation correction — 2026-10-24T21:53:05+05:30

- Tool: Codex.
- Task: correct the organizer-shared template to Devin Hack Kochi and clarify
  that the event has no major AI usage constraints.
- Affected files: `.github/pull_request_template.md`, `AGENTS.md`, `AI_USAGE.md`, `CHANGELOG.md`, `README.md`, `RULES.md`, `SUBMISSION.md`.
- Human review: pending maintainer review of this pull request.
- Validation: documentation diff, whitespace, and local Markdown link checks;
  no application code changed and no runtime checks were needed.
