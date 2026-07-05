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
