# SocialToAI skills: ask for the finished work, not the API call

[中文](README.zh.md)

Nine skills that let your AI read public social media and hand back a finished job. **They read public content and do not post.** Your own platform accounts stay out of it. Published by the SocialToAI team.

## What you get back

A recorded run on the live service, 2026-10-18 ([whole run](https://socialtoai.com/docs/guides/read-reddit-and-x-for-product-complaints/?utm_source=github&utm_medium=repo&utm_campaign=socialtoai-skills-20261106)):

> **You:** What do people complain about with standing desks on Reddit and X?
>
> **Your AI:** 173 comments read, 162 could be judged, 55 complain. Back and neck pain 12% (20 comments), forgetting to switch 11% (18), sore feet 8% (13), each linked to its comment.
>
> **Spent:** 88 credits, $0.29.

The work happens on our side, so your AI does not spend tens of thousands of tokens stitching calls together.

## Install

```bash
# Any agent that reads Agent Skills: Claude Code, Codex, Cursor and more
npx skills add socialtoai/socialtoai-skills

# Only one skill
npx skills add socialtoai/socialtoai-skills --skill wechat-account-digest
```

```bash
# Claude Code plugin: also brings the MCP connection
/plugin marketplace add socialtoai/socialtoai-skills
/plugin install socialtoai@socialtoai
/mcp
```

Without the plugin, your AI asks you to connect the first time: one command or one address, then sign in. Signing in creates the account with **100 free credits, no card**. If credits run out midway, the skill hands over what is finished, gives you a link to buy more, and continues from where it stopped.

## The skills

Credits checked on 2026-11-05. Each skill states its cost and quotes before larger runs.

| Skill | You hand it | You get | Credits, about | Example |
| --- | --- | --- | --- | --- |
| `reddit-x-complaints` | A product | Complaint clusters with shares, wishes, switching signals | 88 | [recorded](plugins/socialtoai/skills/reddit-x-complaints/examples/example.md) |
| `xiaohongshu-competitor-notes` | Competitor links or a keyword | Which notes beat the usual, taken apart, plus note ideas | 126–186 | [recorded](plugins/socialtoai/skills/xiaohongshu-competitor-notes/examples/example.md) |
| `douyin-comment-pain-points` | Video links or a keyword | Pain points ranked, in commenters' words | 62 | [recorded](plugins/socialtoai/skills/douyin-comment-pain-points/examples/example.md) |
| `comment-purchase-drivers` | Posts about a product | Why people buy and hesitate, with draft selling points | 62–132 | [recorded](plugins/socialtoai/skills/comment-purchase-drivers/examples/example.md) |
| `weekly-brand-report` | A brand and competitors | A report you can forward, compared with last week | 36–348 a week | [recorded](plugins/socialtoai/skills/weekly-brand-report/examples/example.md) |
| `overseas-reputation-check` | A brand's English name | Sentiment abroad, risk signals, English quotes with translations | 214 | [recorded](plugins/socialtoai/skills/overseas-reputation-check/examples/example.md) |
| `creator-shortlist` | A niche and a brief | A first-pass list with fit and red flags | 139 (Douyin) | [recorded](plugins/socialtoai/skills/creator-shortlist/examples/example.md) |
| `trending-topic-ideas` | A niche | 10 ideas with evidence from hot lists and breakouts | 118 | [recorded](plugins/socialtoai/skills/trending-topic-ideas/examples/example.md) |
| `wechat-account-digest` | An article link | A digest of the account, and an optional daily watch | 72 | [format only, not a recording](plugins/socialtoai/skills/wechat-account-digest/examples/example.md) |

Examples marked recorded are built from recorded runs; each says which parts came from the run. `socialtoai` is the reference skill behind them, with every platform, call and price (216 calls on 18 platforms). Current prices, no key: https://api.socialtoai.com/v1/capabilities . $10 buys 3,000 credits; failed calls are free.

## Connect any other client

MCP address: `https://mcp.socialtoai.com/mcp`. Setup for each client: [socialtoai-mcp](https://github.com/socialtoai/socialtoai-mcp).

Support: support@socialtoai.com. MIT licence. Published by the SocialToAI team.
