# Investigate ADR Provenance Before Editing

Paste this steering message into the current **VS Code Copilot Agent** conversation if it discovers cited ADRs on unmerged branches or conflicting ADR identifiers.

```text
Pause before making edits, staging, or committing.

The ADR discovery changes the task. First produce a read-only provenance report for each relevant ADR:

| ADR ID | Title/general purpose | Branch | Commit | Relationship to current branch | Approval/merge status | Current citations | Collision | Authority known? |
|---|---|---|---|---|---|---|---|---|

Verify from Git history whether each branch is active, abandoned, superseded, or awaiting review. Do not infer authority merely because a document exists.

For the ID collision, identify both documents and their histories without reproducing sensitive content. Do not renumber, cherry-pick, restore, merge, or rewrite either ADR.

Classify each current citation as:

- supported by an approved decision;
- supported only by an unmerged proposal;
- contradicted or ambiguous;
- unknown pending team confirmation.

If approval status cannot be established locally, record a concise team-confirmation question. Do not downgrade or preserve the citation yet.

Then continue the inventory investigation read-only. Stop with the provenance table and recommended next decision; make no repository changes.
```
