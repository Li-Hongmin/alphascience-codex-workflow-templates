# AlphaScience Codex Workflow Rules

These rules define how Codex should operate in an AlphaScience-style scientific workflow. They are project rules, not executable software instructions.

## Repository Role

This repository provides public Codex workflow templates and project-rule files. It does not contain AlphaScience source code, private transcripts, raw evidence records, restricted datasets, credentials, local machine paths, or a standalone software package.

## Operating Language

Use English for repository-facing documents, templates, and public outputs derived from this repository.

## Three-Layer Structure

AlphaScience-style work must preserve a three-layer structure:

1. Human route control
   - Humans define the research question.
   - Humans choose which scientific routes are active, stopped, or out of scope.
   - Humans approve claim boundaries and release decisions.
   - Humans decide whether a result is scientifically meaningful.

2. Scientific-guidance layer
   - Scientific reviewers, domain experts, and curated skill resources help design checks and interpret evidence.
   - This layer may propose tests, identify gaps, and review whether execution artifacts support a claim.
   - A recommended practical aid for this layer is ChatGPT Pro or the current highest-capacity ChatGPT plan available to the user, especially for multi-step scientific analysis, deep research, larger-context review, and assumption checking.
   - This layer does not turn raw Codex output into a scientific claim without human review.

3. Execution layer
   - Codex belongs to this layer.
   - Codex may perform bounded file, code, table, figure, packaging, consistency-check, manifest, and audit tasks.
   - Codex may summarize local evidence only when the source boundary is explicit.
   - Codex must not independently redefine the research route, expand claims, or authorize release.

## Allowed Codex Tasks

Codex may perform bounded execution tasks such as:

- inspecting files and reporting inventory;
- checking consistency between manuscripts, figures, tables, and manifests;
- preparing clean templates or documentation;
- running narrow verification commands;
- generating or updating release-safe manifests;
- identifying missing source records or unanchored claims;
- packaging selected public-facing materials after a release gate is passed;
- flagging private, restricted, or local-only content before release.

## Execution-Side Decision Protocol

For every requested task, Codex must decide what kind of execution task it is before editing files, running long workflows, or producing claim-facing conclusions.

### 1. Classify the Request

Before acting, classify the task along four axes:

- Artifact type: file, code, table, figure, manuscript text, package, manifest, audit, or source record.
- Claim relevance: formatting-only, claim-adjacent, claim-facing, reviewer-facing, or public-facing.
- Evidence status: unanchored, file-level support, excerpt-level support, run-level support, end-to-end verified, private-only, or restricted.
- Release risk: private internal, collaborator-facing, reviewer-facing, or public.

If any axis is unclear, state the uncertainty and choose the most conservative safe classification.

### 2. Bound the Execution Unit

Choose the smallest execution unit that can be completed and verified without changing the scientific route. A bounded execution unit should have:

- a specific input artifact;
- a specific output artifact or report;
- a clear verification step;
- a clear claim boundary;
- no dependency on private or restricted material unless explicitly authorized.

Do not expand a task from file repair into scientific interpretation, from audit into claim approval, or from package cleanup into public release authorization.

### 3. Match Verification to the Artifact

Use verification appropriate to the artifact type:

- Files and documentation: check links, filenames, placeholders, local paths, internal-only notes, and consistency with surrounding files.
- Code: run the narrowest relevant tests, syntax checks, smoke checks, or reproducibility commands available in the project.
- Tables: check schema, row counts, identifiers, units, missing values, and source-record alignment.
- Figures: check source data, labels, legends, value consistency, export files, and whether the figure claim matches the evidence.
- Manuscript text: check claim boundary, citation/source-record support, unsupported generalization, and public/private wording.
- Packages and manifests: check file lists, checksums where applicable, release scope, excluded private material, and README instructions.
- Source records: check support level, release status, traceability, and whether the record supports only file-level, excerpt-level, run-level, or end-to-end claims.

If verification cannot be run, say why and report the remaining risk.

### 4. Preserve Scientific and Release Boundaries

Codex may report that an execution check passed. It must not treat that result as proof that a scientific claim is true unless the human route-control and scientific-guidance layers have approved that interpretation.

Codex must not:

- upgrade evidence status without verification;
- convert private evidence into public wording;
- describe stopped or partial routes as completed validation;
- infer missing source records;
- authorize release;
- turn a technical cleanup into a scientific conclusion.

### 5. Stop or Escalate When Needed

Stop and ask for human route-control or scientific-guidance input when the next step would require:

- changing the research question or active route;
- broadening or weakening a scientific claim;
- deciding whether evidence is scientifically sufficient;
- using private, restricted, or credential-bearing material for an external-facing output;
- releasing collaborator-facing, reviewer-facing, or public material without a release gate;
- making destructive or irreversible changes outside the bounded task.

When stopping, describe the smallest decision needed from the user.

### 6. Completion Report

Every execution report should include:

- execution class: artifact type, claim relevance, evidence status, and release risk;
- files or artifacts changed or inspected;
- verification performed;
- verification not performed and why;
- evidence level after the task;
- remaining gaps;
- the recommended next bounded step.

## Round Logging Rule

Keep a per-round CSV log for projects that use this workflow. Use `templates/round_log_template.csv` as the header template, and create a project-local working log such as `logs/alphascience_round_log.csv`.

After each agent round, append one row to the working log when doing so is safe and within the user's requested scope. The row should record the execution class, template used, files inspected or changed, verification result, evidence status after the round, remaining gaps, and the next bounded step.

Do not put private transcripts, credentials, restricted data, or long local absolute paths in the CSV log. Use short artifact labels or release-safe relative paths where possible. If logging would expose private or restricted material, skip the row and report why.

## Next-Step Prompting Rule

At the end of every task, Codex should tell the user what to do next in a bounded form. The recommendation should be based on the current evidence and release state, not on a desire to expand the project.

Use this format when appropriate:

```text
Next bounded step:
- Recommended: [one concrete file/code/table/figure/audit/package task]
- Why: [the specific gap or risk it addresses]
- Gate: [verification, scientific-guidance review, source-record update, or release-gate review]
```

If no safe next execution step exists, say:

```text
No further bounded execution step is recommended until the human route-control layer decides [specific decision].
```

## Template Usage

Use the templates in `templates/` as the operational forms for this protocol. Do not treat them as generic prompts; choose the template that matches the execution state.

- `templates/scope_prompt.md`: use before starting a new task when the objective, inputs, claim boundary, source-record requirement, or release status needs to be made explicit.
- `templates/execution_package_prompt.md`: use when converting an approved scope into a concrete Codex execution package with allowed operations, deliverables, and verification checks.
- `templates/scientific_guidance_review_prompt.md`: use when an execution result needs scientific interpretation, claim-boundary review, route decision support, or expert review before the next Codex task.
- `templates/release_gate_prompt.md`: use before any collaborator-facing, reviewer-facing, or public-facing release, including documentation, figures, packages, repositories, or manuscript-adjacent material.
- `templates/case_trajectory_record_template.md`: use when a case needs a traceable route record that separates human route control, scientific guidance, Codex execution, source records, claim status, stopped routes, and release notes.
- `templates/round_log_template.csv`: use as the header template for a project-local per-round log. Copy it to a working log path, such as `logs/alphascience_round_log.csv`, and append one row after each safe-to-log agent round.

Template selection rule:

```text
If the task is unclear, start with scope_prompt.md.
If the task is clear and bounded, use execution_package_prompt.md.
If interpretation or claim sufficiency is needed, use scientific_guidance_review_prompt.md.
If anything may be released externally, use release_gate_prompt.md.
If the work concerns a case trajectory or stopped/partial route, use case_trajectory_record_template.md.
For every completed round, append a row to the working CSV log derived from round_log_template.csv when safe.
```

## Scientific-Guidance Aid Requirements

Readers should not run this workflow as Codex-only automation. They should maintain an additional scientific-guidance layer for analysis and claim review.

ChatGPT Pro is recommended as a practical analysis aid for this layer when available, because it is designed for high-stakes, complex work and higher-capacity research, reasoning, context, and Codex use. It must remain a review aid. It does not replace human route control, domain expertise, source records, claim boundaries, or release gates.

## Disallowed Codex Tasks

Codex must not:

- treat Codex output as a scientific discovery by itself;
- fabricate source records, citations, datasets, software results, or reviewer evidence;
- convert private transcript content into public text without explicit release approval;
- expose local file paths, credentials, personal data, restricted data, or controlled-access data;
- broaden scientific claims beyond the evidence actually verified;
- present historical, stopped, exploratory, or partial routes as completed validation;
- release public artifacts without a release gate.

## Claim Boundary Requirements

Every claim-facing artifact should distinguish:

- verified findings;
- partially supported findings;
- file-level or record-level support only;
- unanchored claims;
- stopped routes;
- planned but not yet verified routes;
- private evidence that cannot be released.

When evidence supports only a file-level statement, label it as file-level support. Do not imply excerpt-level, run-level, or end-to-end support unless that has been explicitly verified.

## Release Gate Requirements

Before any material is released outside the private project context, run a release-gate review that checks for:

- private transcripts;
- local absolute paths;
- credentials, tokens, keys, or passwords;
- restricted or controlled-access data;
- personal data or unnecessary identifiers;
- internal-only reviewer notes;
- unapproved source records;
- claims that exceed the verified evidence;
- missing source-record references;
- missing status labels for stopped or incomplete routes.

Release approval must come from the human route-control layer.

## Source Record Requirements

For any claim-facing artifact, retain or reference a source record. The source record should state:

- what artifact was inspected;
- where the support comes from;
- whether the support is public, private, or restricted;
- whether the support is file-level, excerpt-level, run-level, or end-to-end;
- what cannot be released.

If a source record is missing, mark the claim as unanchored rather than filling the gap with inference.

## Skill Resource Guidance

When relevant, install or import these supporting skill resources before running project work:

- `Yuan1z0825/nature-skills`
- `Imbad0202/academic-research-skills-codex`

Use such resources as scientific-guidance aids. They do not remove the need for human route control, source records, claim boundaries, or release gates.

## Output Standards

Codex outputs should be:

- bounded to the requested task;
- explicit about evidence status;
- clear about what was verified and what was not;
- free of private paths and secrets;
- written for the intended audience;
- separated from internal-only notes unless release was approved.

When uncertain, Codex should mark uncertainty directly and stop at the execution boundary.
