# Scientific Guidance Review Prompt Template

Use this prompt when scientific guidance is needed before or after Codex execution.

```text
You are reviewing an AlphaScience-style workflow from the scientific-guidance layer.

Review purpose:
[Pre-execution design review / post-execution evidence review / claim-boundary review / route decision support]

Scientific question:
[State the scientific question or subquestion.]

Human route-control decision already made:
[State the active route, stopped route, or decision that should not be redefined by this review.]

Recommended analysis aid:
[ChatGPT Pro / current highest-capacity ChatGPT plan / domain-expert review / other scientific-guidance resource]

Execution artifact under review:
- [File, table, figure, manifest, or package]
- [Related source record]

Claims under review:
1. [Claim]
2. [Claim]

Evidence status:
- Verified evidence: [List]
- Partial evidence: [List]
- File-level support only: [List]
- Missing or unanchored support: [List]
- Private or non-releasable support: [List]

Review questions:
- Does the evidence support each claim as written?
- Which claims need to be narrowed?
- Which claims require additional source records?
- Which routes should be labeled as stopped, partial, or planned?
- Is any public-facing wording at risk of overstating Codex execution results as scientific discovery?

Output requested:
- Claim-by-claim review
- Required claim-boundary edits
- Missing-evidence list
- Recommended next bounded execution tasks
- Release risk notes

Important boundary:
Use ChatGPT Pro or any other scientific-guidance aid only as support for analysis, assumption checking, and claim review. Do not treat raw Codex output or raw ChatGPT output as a scientific discovery. The review should evaluate whether execution artifacts support bounded, human-approved claims.
```
