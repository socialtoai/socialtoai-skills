# SocialToAI Skills

Six optional, editable research workflows for AI clients connected to [SocialToAI](https://socialtoai.com), the social media data gateway for AI agents. Version 0.1.0 · Contract v1.

| Skill | Use it for |
|---|---|
| `socialtoai-setup` | Connect your client, test free capability discovery, configure preferences |
| `socialtoai-research` | Route a general public-social question to suitable platforms and a bounded call sequence |
| `socialtoai-benchmarks` | Compare relevant creators with compatible metrics |
| `socialtoai-viral-analysis` | Inspect a post and its audience response, separating evidence from hypotheses |
| `socialtoai-pain-points` | Collect problems, workarounds and counterexamples from public discussion |
| `socialtoai-topic-research` | Turn sourced audience questions into a topic shortlist |

## Install

```bash
npx skills add socialtoai/socialtoai-skills --agent codex --skill socialtoai-research
```

Choose another supported agent (`claude-code`, `cursor`, `gemini`, …) or another Skill name. Installation writes configuration only; connect SocialToAI separately by Remote MCP using the URL from your [console](https://socialtoai.com/console/) and the [quickstart](https://socialtoai.com/docs/quickstart/). Skills contain no credentials and no telemetry.

## Upgrade, fork, remove

- Upgrade: run the install command again and review replaced files. Keep your own edits in a separately named fork so official upgrades cannot overwrite them.
- Fork: copy a workflow into a new folder, rename it in the frontmatter, then add your industry vocabulary or competitor shortlist. Keep credentials out of Skills.
- Remove: `npx skills remove socialtoai-research` from the same project scope, then confirm your client no longer discovers it. Removing a Skill does not disconnect MCP or revoke a Key.

## What a Skill can and cannot establish

Every workflow enforces a budget, source citation, fallback disclosure and stop rules. Those are instructions for the model, not proof of model compliance or research quality. Public samples do not establish market share or private ranking algorithms. Prices and filters referenced in `references/platforms.md` are generated from the same reference cards as socialtoai.com; check current tool descriptions before relying on them.

## License

MIT — see [LICENSE](LICENSE).
