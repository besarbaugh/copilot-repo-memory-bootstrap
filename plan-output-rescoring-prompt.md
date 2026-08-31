# Rescore Phase A from Complete Plan Outputs

Paste this into the same VS Code Copilot Agent chat that scored the three Phase A runs. Then provide each complete Plan response produced before **Start Implementation**, clearly labeled `Run 1`, `Run 2`, and `Run 3`.

```text
I will now provide the complete pre-handoff Plan output for each run, labeled Run 1, Run 2, and Run 3.

Before rescoring:

1. Verify Run 1's actual test location from the repository and authoritative development documentation. Do not assume it belongs under `tests/unit/`.
2. Use the full Plan outputs to rescore evidence labeling, tier and concision, and every other dimension that cannot be attributed to Plan from the Agent handoff alone.
3. Keep Run 3 classified as a supplemental regression probe, not Matrix Scenario 11.
4. Do not edit the matrix, instructions, skills, application files, or test files yet.
5. Report the revised scores, direct supporting evidence, and remaining unknowns only.
6. Do not infer a pass from the Agent handoff when the dimension evaluates Plan behavior.

Use `pass`, `fail`, `unknown`, or `not applicable` for each dimension. If evidence is incomplete, choose `unknown` and state exactly what is missing.

Do not reproduce secrets, internal URLs, private ticket content, customer information, employee information, personal information, or proprietary source excerpts. Generalize sensitive details and report `[sensitive content detected: review locally]` with only the repository-relative path.

Wait for all three complete Plan outputs before rescoring. Make no repository changes.
```
