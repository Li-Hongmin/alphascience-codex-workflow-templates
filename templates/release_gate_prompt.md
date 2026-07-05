# Release Gate Prompt Template

Use this prompt before any collaborator-facing or public-facing release.

```text
You are performing an AlphaScience-style release-gate review.

Release candidate:
[Name of package, manuscript section, figure set, template set, or repository]

Intended audience:
[Private internal / collaborator-facing / reviewer-facing / public]

Release authority:
[Human approver or decision record]

Materials to inspect:
- [File or folder]
- [File or folder]

Materials explicitly out of scope:
- [File or folder]
- [Private records not approved for release]

Release-gate checks:
1. Private transcript scan
   - Confirm that no private transcript, raw chat log, or unreleased conversation content is included.

2. Local-path scan
   - Confirm that public-facing files do not expose local absolute paths or machine-specific storage paths.

3. Credential and secret scan
   - Confirm that there are no credentials, tokens, keys, passwords, cookies, or private configuration files.

4. Restricted-data scan
   - Confirm that controlled-access data, nonredistributable data, and restricted data derivatives are excluded or explicitly authorized.

5. Claim-boundary scan
   - Confirm that every scientific claim is labeled as verified, partially supported, file-level only, planned, stopped, or unanchored.
   - Confirm that Codex execution artifacts are not described as independent scientific discovery.

6. Source-record scan
   - Confirm that claim-facing statements point to source records or are marked as unanchored.

7. Package-role scan
   - Confirm that the material is described as the correct type of release: template repository, documentation, reviewer package, code package, data package, or manuscript supplement.

8. License and reuse scan
   - Confirm whether reuse terms are present and appropriate for the intended release.

Required output:
- Release decision: pass / pass with conditions / fail
- Blocking issues
- Non-blocking issues
- Files inspected
- Claims requiring narrower wording
- Source-record gaps
- Required edits before release

Do not publish or push release materials until the human route-control layer approves the release decision.
```
