# AlphaScience Codex Workflow Templates

This repository provides Codex workflow templates and project rules, not AlphaScience source code or a standalone software package.

The materials here document a conservative workflow pattern for using Codex in AI-assisted scientific work. The core idea is to keep scientific route control, scientific interpretation, execution, and release decisions separate.

## Repository Role

This repository is a public documentation companion for the manuscript:

> Calibrating scientific claims in AI-assisted science with AlphaScience

It contains reusable project rules and prompt templates for bounded Codex execution tasks. It does not contain private AlphaScience transcripts, unpublished raw records, controlled-access data, credentials, local machine paths, active subproject code, or executable research software.

## Quick Start

1. Install or import the supporting skill resources used by the workflow:
   - [Yuan1z0825/nature-skills](https://github.com/Yuan1z0825/nature-skills)
   - [Imbad0202/academic-research-skills-codex](https://github.com/Imbad0202/academic-research-skills-codex)

2. Copy or adapt [`AGENTS.md`](AGENTS.md) into the root of a project where Codex will operate.

3. Use the templates in [`templates/`](templates/) to define bounded tasks:
   - [`scope_prompt.md`](templates/scope_prompt.md)
   - [`execution_package_prompt.md`](templates/execution_package_prompt.md)
   - [`scientific_guidance_review_prompt.md`](templates/scientific_guidance_review_prompt.md)
   - [`release_gate_prompt.md`](templates/release_gate_prompt.md)
   - [`case_trajectory_record_template.md`](templates/case_trajectory_record_template.md)

4. Run Codex only on bounded file, code, table, figure, packaging, or audit tasks. Do not treat raw Codex output as a scientific discovery or as publication-ready evidence.

## Layer Model

The workflow separates three layers:

- Human route control: humans choose the research question, decide which routes matter, approve claim boundaries, and authorize release.
- Scientific-guidance layer: scientific reviewers, domain experts, and curated skill resources propose checks, interpret evidence, and review whether an execution result supports a claim.
- Execution layer: Codex performs bounded file, code, table, figure, package, and audit work under explicit instructions and verification gates.

Codex is assigned to the execution layer. It may help prepare artifacts for scientific review, but it does not replace route control, domain interpretation, or release authorization.

## Required Boundaries

Any project using these templates should preserve the following boundaries:

- Claim boundary: every output should state what is supported, what is not supported, and what remains unverified.
- Release gate: public or collaborator-facing artifacts require an explicit pre-release scan and approval step.
- Source record: claims should be tied to traceable, retained source records or explicitly marked as unanchored.
- Privacy boundary: do not release private transcripts, local file paths, credentials, personal data, restricted data, or controlled-access materials.
- Role boundary: do not describe Codex-generated execution artifacts as independent scientific discovery.

## Code Availability Language

Suggested manuscript wording:

```tex
No source code or standalone software package is released with this manuscript.
Codex workflow-template materials and project-rule files used to document the
analysed AlphaScience workflow are available at
https://github.com/Li-Hongmin/alphascience-codex-workflow-templates. These
materials are documentation and workflow templates, not executable source code.
```

## Repository Contents

```text
.
|-- AGENTS.md
|-- README.md
`-- templates/
    |-- case_trajectory_record_template.md
    |-- execution_package_prompt.md
    |-- release_gate_prompt.md
    |-- scientific_guidance_review_prompt.md
    `-- scope_prompt.md
```

## What This Repository Is Not

This repository is not:

- an AlphaScience source-code release;
- a standalone software package;
- a data repository;
- a full reproducibility package;
- a transcript archive;
- a benchmark suite;
- an autonomous scientific-discovery system.

It is a small public template repository for documenting how bounded Codex execution tasks were governed.
