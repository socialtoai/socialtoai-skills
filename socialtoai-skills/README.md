# SocialToAI product Skills

Version 0.1.0 · Contract v1 · Six product workflows.

These are implementation-stage assets. Comparative model effectiveness is **unvalidated**; no production-readiness or task-improvement claim follows from structural checks. The current historical Mock report is not a fresh Skill baseline. Launch ticket 31 requires current model/task evidence before the full launch acceptance closes.

The packages use only SocialToAI core verbs plus free capabilities discovery. They contain no supplier endpoints, credentials or development-agent instructions. Their domain source is the approved product methodology and public contract, reflected in the bundled reference material.

From this directory's parent, install a local package with `npx skills add ./socialtoai-skills --agent codex --skill socialtoai-research`. Choose another supported agent or one of the other five names. Public repository/download distribution is prepared here and activated by launch ticket 36; do not invent a public owner/repo URL.

Before upgrading, copy your own changes into a separately named local fork. Reinstalling official files may replace edits. Keep private industry terms and competitor lists in your own fork; do not place credentials in Skills. To uninstall use `npx skills remove <skill-name>` from the same project scope, then verify the client no longer discovers it. Removing a Skill does not remove the MCP connection or revoke a Key; use client MCP settings or Access for those actions.

Routing cases were written before the bodies in `evals/trigger-cases.jsonl`; `evals/task-contracts.json` defines budget, downgrade, evidence, cursor, setup and sampling behavior. Run in fresh contexts and preserve outputs; never mark a model case passed from regex or file shape alone.

For a complete project uninstall, omit `--agent`: clients share `.agents/skills`, so removing only one agent link can leave the Skill discoverable. Inspect `npx skills list --json` after removal. This removes the named official Skill across the project, not separately named forks. Use `DISABLE_TELEMETRY=1` if you want to disable the third-party installer's usage telemetry.
