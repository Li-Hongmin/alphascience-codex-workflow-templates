# AlphaScience Codex Workflow Templates

This repository provides Codex workflow templates and project rules, not AlphaScience source code or a standalone software package.

The materials here document a conservative workflow pattern for using Codex in AI-assisted scientific work. The core idea is to keep scientific route control, scientific interpretation, execution, and release decisions separate.

## Repository Role

This repository is a public documentation companion for the manuscript:

> Calibrating scientific claims in AI-assisted science with AlphaScience

It contains reusable project rules and prompt templates for bounded Codex execution tasks. It does not contain private AlphaScience transcripts, unpublished raw records, controlled-access data, credentials, local machine paths, active subproject code, or executable research software.

## Quick Start

Open Claude Code or Codex at the root of the project you want to configure. Copy the following prompt into the agent and let it install or adapt the workflow materials for that project.

```text
You are bootstrapping AlphaScience-style Codex workflow rules into this project.

Source repository:
https://github.com/Li-Hongmin/alphascience-codex-workflow-templates

Required supporting skill resources:
- https://github.com/Yuan1z0825/nature-skills
- https://github.com/Imbad0202/academic-research-skills-codex

Goal:
Install or import the supporting skill resources when the local agent environment supports skill installation. Then copy or adapt the AlphaScience workflow rules and prompt templates into this project.

Before changing files:
1. Inspect the current project root.
2. Check whether AGENTS.md already exists.
3. If AGENTS.md exists, do not overwrite it blindly. Merge the AlphaScience workflow rules into the existing project rules, preserving more specific local instructions.
4. If templates/ already exists, add only the missing AlphaScience workflow templates or clearly report any naming conflict before changing it.

Files to install or adapt from the source repository:
- AGENTS.md
- templates/scope_prompt.md
- templates/execution_package_prompt.md
- templates/scientific_guidance_review_prompt.md
- templates/release_gate_prompt.md
- templates/case_trajectory_record_template.md

Scientific-guidance layer:
Set up a separate scientific-guidance layer before assigning Codex execution work. A recommended practical option is ChatGPT Pro, alongside human domain review, for high-capacity scientific analysis, deep research, larger-context review, assumption checking, and multi-step reasoning.

Execution boundary:
Codex should be used only for bounded file, code, table, figure, package, manifest, and audit tasks. Do not treat raw Codex output or raw ChatGPT output as a scientific discovery or as publication-ready evidence.

Required boundaries:
- Preserve human route control.
- Preserve claim boundaries.
- Preserve source records.
- Run a release gate before public or collaborator-facing output.
- Do not expose private transcripts, local paths, credentials, restricted data, or controlled-access material.
- Mark missing evidence as missing instead of inventing support.

After installation:
1. Report which files were created or merged.
2. Report whether the two supporting skill resources were installed, imported, or only referenced.
3. Confirm that no private transcript, local absolute path, credential, or restricted-data material was introduced.
4. Suggest the first bounded execution task that should be run with the installed templates.
```

After bootstrapping, use the installed templates to define bounded execution packages. Codex should remain in the execution layer; scientific interpretation and release approval remain outside Codex.

## Layer Model

The workflow separates three layers:

- Human route control: humans choose the research question, decide which routes matter, approve claim boundaries, and authorize release.
- Scientific-guidance layer: scientific reviewers, domain experts, and curated skill resources propose checks, interpret evidence, and review whether an execution result supports a claim.
- Execution layer: Codex performs bounded file, code, table, figure, package, and audit work under explicit instructions and verification gates.

Codex is assigned to the execution layer. It may help prepare artifacts for scientific review, but it does not replace route control, domain interpretation, or release authorization.

## Scientific-Guidance Aid

Readers who reuse these templates should pair Codex execution with a separate scientific-guidance layer. This layer should help analyze scientific meaning, inspect assumptions, design checks, review claim boundaries, and decide whether execution artifacts actually support a claim.

For individual researchers or small teams, ChatGPT Pro is a recommended practical aid for this layer because OpenAI describes it as providing Pro reasoning, maximum deep research and agent mode, maximum memory and context, and expanded Codex capacity. It should be used as an analysis and review aid, not as an automatic source of scientific truth. Domain experts and human route-control decisions remain required.

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
