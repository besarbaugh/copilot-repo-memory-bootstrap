# Resolve Pre-Test Copilot Rebuild Blockers

Paste this prompt into **VS Code Copilot Chat with Agent selected** on the computer containing the target work repository. It addresses only verified blockers before the fresh-chat Plan-to-Agent matrix.

```text
Resolve only the objective pre-test blockers from the post-rebuild audit. Do not redesign instructions, alter Plan wording, reclassify skills, modify application code, push, or merge.

Work on the current rebuild branch.

## 1. Investigate missing ADR citations

Search the current tree, rebuild baseline, and reachable pre-rebuild history for the two cited ADR decisions.

Do not create an ADR merely to satisfy a reference.

For each citation:

- If an authoritative decision document exists, restore or correct the link without inventing content.
- If no authoritative decision exists, remove the claim of ADR authority and record the unresolved decision in the existing open-questions document.
- Preserve any underlying safety constraint only when independently supported by current code, configuration, or authoritative documentation.
- Label unsupported claims as unknown or requiring team confirmation.

Report paths and generalized findings, not proprietary content.

## 2. Repair the stale customization inventory

Determine whether the inventory is:

- generated from a manifest;
- maintained manually;
- or owned by an external installer.

Then repair it through its authoritative source:

- regenerate it if generated;
- remove only the deleted-agent entry if manually maintained;
- stop and report the owner if an external tool controls it.

Confirm no remaining reference points to the deleted custom agent.

## 3. Handle the flagged untracked document safely

Do not print, stage, commit, delete, or rewrite its contents.

Report only:

- whether it is already ignored;
- the general secret-pattern category detected;
- whether the match appears structural or value-bearing;
- whether the file is needed by Copilot customization discovery.

Stop and ask me to choose between locally scrubbing it, adding an appropriate ignore rule, or removing it locally.

## Validation

After resolving sections 1 and 2:

- search for every stale ADR and deleted-agent reference;
- validate Markdown links and skill frontmatter;
- run the customization inventory's native validation, if one exists;
- run `git diff --check`;
- secret-scan only the proposed tracked diff;
- confirm no application files changed.

Show the complete staged diff before committing.

Create one commit for the verified configuration corrections using the repository's required commit-message convention. Do not push.

End with:

# Pre-Test Blocker Resolution

| Blocker | Resolution | Evidence | Remaining risk |
|---|---|---|---|

State whether the branch is ready for the existing fresh-chat Plan-to-Agent matrix. Do not claim it is ready to merge.
```
