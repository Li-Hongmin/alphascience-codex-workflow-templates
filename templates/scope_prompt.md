# Scope Prompt Template

Use this prompt before assigning a bounded Codex execution task.

```text
You are working in an AlphaScience-style workflow.

Role boundary:
- Human route control defines the research direction, active route, claim boundary, and release decision.
- Scientific guidance may propose checks and interpret evidence.
- Codex acts only as the execution layer for bounded file, code, table, figure, package, or audit work.

Task title:
[Short task title]

Objective:
[Describe the bounded execution objective in one or two sentences.]

Project context:
[Describe only the context needed for this task. Do not paste private transcripts unless explicitly approved.]

Allowed inputs:
- [File, folder, table, manuscript section, figure, or manifest]
- [Additional allowed source]

Forbidden inputs:
- Private transcripts unless explicitly listed above
- Credentials, tokens, passwords, or keys
- Restricted or controlled-access data
- Local-only recovery folders unless explicitly approved
- Any unrelated project material

Claim boundary:
[State what the task may support and what it must not claim.]

Source-record requirement:
[Describe the source record, manifest, checksum, or evidence anchor expected for the task.]

Expected output:
- [Artifact 1]
- [Artifact 2]
- [Short written summary]

Verification:
- [Command, visual check, checksum, table consistency check, or manual review step]

Release status:
[Private only / collaborator-facing draft / public-facing candidate / release-approved]

Stop conditions:
- Stop if the task requires changing the scientific route.
- Stop if evidence is missing for a claim-facing statement.
- Stop if private, restricted, or credential-bearing content is encountered.
- Stop if the requested output would exceed the approved release status.
```
