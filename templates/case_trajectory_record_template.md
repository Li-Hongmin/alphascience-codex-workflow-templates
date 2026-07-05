# Case Trajectory Record Template

Use this template to record the trajectory of one AlphaScience-style case without exposing private transcripts or unsupported claims.

## Case Metadata

- Case ID:
- Case title:
- Date opened:
- Date last updated:
- Current status: active / stopped / partial / verified / archived / release-approved
- Intended audience: private internal / collaborator-facing / reviewer-facing / public

## Human Route Control

- Research question:
- Active route selected by human route control:
- Stopped or rejected routes:
- Reason for current route:
- Release decision status:

## Scientific-Guidance Layer

- Scientific guidance sources used:
- Domain assumptions:
- Checks requested:
- Interpretation notes:
- Claims requiring expert review:

## Execution Layer

- Codex execution tasks performed:
- Files, tables, figures, or manifests inspected:
- Commands or checks run:
- Artifacts generated:
- Execution limitations:

## Source Records

| Source record ID | Artifact | Support level | Release status | Notes |
| --- | --- | --- | --- | --- |
|  |  | file-level / excerpt-level / run-level / end-to-end | public / private / restricted |  |

## Claim Boundary

| Claim | Status | Support | Boundary wording |
| --- | --- | --- | --- |
|  | verified / partial / file-level only / planned / stopped / unanchored |  |  |

## Negative, Stopped, or Partial Routes

- Route:
  - Status:
  - Reason:
  - Evidence retained:
  - Public wording allowed:

## Verification

- Verification performed:
- Verification result:
- Remaining unverified items:
- Required next bounded execution task:

## Release Gate Notes

- Private transcript included: no / yes, remove before release
- Local absolute path included: no / yes, remove before release
- Credentials or secrets included: no / yes, remove before release
- Restricted data included: no / yes, authorization required
- Claims exceed evidence: no / yes, narrow before release
- Source-record gaps: no / yes, list below

## Public-Facing Summary Candidate

Write only release-safe text here. Do not include private transcripts, local paths, credentials, restricted data, or claims beyond the verified evidence.

```text
[Public-facing case summary candidate]
```
