# Run Staged Native Plan-to-Agent Validation

Paste this prompt into the current **VS Code Copilot Agent** conversation after the pre-test inventory correction is committed. Agent prepares and records the tests; you run each test in a separate fresh Plan chat.

```text
Return to the primary objective: behaviorally validate the native Plan-to-Agent workflow.

Do not update registry resources, repair missing companion bundles, edit ADR citations, reclassify skills, alter instructions, push, merge, or modify application files. Those are separate follow-ups.

Use evidence-based terms such as documented procedure, repository convention, operating context, or team-confirmed practice. Avoid vague labels for undocumented or team-held context.

## Establish the test source

1. Read the existing Plan-validation matrix and its scoring rubric.
2. Verify its ten scenarios still match current paths and repository behavior.
3. Do not silently repair a stale scenario. Report the mismatch and propose the smallest correction.
4. Use one unchanged model and reasoning setting for comparable runs.

## Phase A: three core scenarios

Select the existing scenarios that cover:

1. A lightweight, single-file change.
2. A detailed cross-cutting change plus Start Implementation handoff.
3. A difficult regression requiring reproduction and a failing test before a fix.

For each, provide a compact execution card:

| Field | Required content |
|---|---|
| Scenario ID | Existing matrix identifier |
| Exact prompt | Ready to paste into a fresh native Plan chat |
| Expected investigation | Specific types of code, tests, configuration, instructions, and decisions to inspect |
| Expected Plan shape | Tier, required sections, and maximum reasonable size |
| Acceptance evidence | Observable behavior and named tests |
| Validation evidence | Exact commands expected from repository documentation |
| Expected References | Instructions, skills, and files that should appear |
| Failure conditions | Objective reasons to fail the run |
| Handoff check | Information Agent must inherit after Start Implementation |

Do not simulate these runs. Stop after presenting the three cards so I can execute them in separate fresh Plan chats.

## How I will test handoff

For a scenario requiring handoff, I will select **Start Implementation**, then immediately send Agent:

> Before modifying files, state the inherited approved decisions, relevant files, acceptance criteria, validation commands, unresolved risks, and first implementation step. Then stop without editing.

The handoff passes only if Agent recovers those items from the approved plan without redesigning the task or relying on omitted chat context.

## Scoring

When I return each Plan output and handoff observation, score these dimensions as `pass`, `fail`, or `unknown` with direct evidence:

1. Repository investigation.
2. Material-question discipline.
3. Verified versus inferred or unknown claims.
4. Decision completeness and non-goals.
5. Observable acceptance criteria.
6. Exact targeted and broader validation commands.
7. Risk and rollback when required.
8. Concision and correct lightweight/detailed tier.
9. Plan-to-Agent handoff fidelity.

Do not award a pass from structure alone.

If an ADR citation appears, treat it as authority from an unmerged proposal unless team approval is independently established. The Plan passes evidence discipline only if it communicates that status rather than presenting the ADR as merged policy.

## Failure confirmation

- If a criterion fails once, rerun the same unchanged scenario in two more fresh chats with the same model and settings.
- Do not change instructions between repetitions.
- Promote an instruction or skill change only after three evidence-backed occurrences and human review.
- Record isolated or nonrepeatable failures without rewriting customization files.

## Phase B: remaining scenarios

If all three Phase A scenarios pass, prepare execution cards for the remaining seven existing matrix scenarios. Keep each run in a separate fresh chat.

Include routing checks for:

- repository-wide versus scoped instructions;
- automatic skill invocation exactly once;
- manual-only skills not invoking automatically;
- unrelated repositories receiving no work-specific user-level context.

The previously discovered missing companion bundles do not block this matrix unless an existing scenario actually invokes an affected skill. If that occurs, mark the result as a packaging failure rather than a Plan-contract failure.

## Recording results

Do not edit the matrix until I return actual outputs or screenshots.

After all evidence is supplied:

1. Fill only the result, evidence, and status fields.
2. Preserve original prompts and acceptance criteria unless a path is objectively stale.
3. List confirmed failures separately from unknown or UI-inaccessible evidence.
4. Show the complete diff before staging.
5. Do not commit until I approve the recorded results.

## Privacy

- Do not reproduce secrets, internal URLs, private ticket content, customer information, employee information, personal information, or proprietary source excerpts.
- Generalize sensitive scenario details while retaining the behavior and validation boundary.
- For sensitive material, report only `[sensitive content detected: review locally]` and its path.

Start by presenting only the three Phase A execution cards.
```
