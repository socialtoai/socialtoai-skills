# SocialToAI skill

[中文](README.zh.md)

SocialToAI is an API and MCP server that lets AI tools read publicly visible social media content (posts, comments, profiles and trends) from 18 platforms, including TikTok, Instagram, X (Twitter), Reddit, YouTube, Xiaohongshu (RedNote), Douyin, Weibo. It is billed in prepaid credits, and failed calls are free.

## Facts

| Fact | |
| --- | --- |
| Platforms (18) | TikTok, Instagram, X (Twitter), Reddit, YouTube, Facebook, LinkedIn, Threads, Telegram, Pinterest, Xiaohongshu (RedNote), Douyin, Weibo, WeChat Articles, Bilibili, Zhihu, Kuaishou, WeChat Channels |
| Ad libraries (2) | Meta Ad Library, Google Ads Transparency |
| Actions (6) | search, trending, detail, comments, user_profile, user_posts, plus a catalog of platform-specific interfaces (find / call) |
| Tools (7) | Brand buzz, Comment analysis, Account watch, Find creators, Creator profile, Bulk link data, Viral finder |
| API | https://api.socialtoai.com/v1 · MCP (Streamable HTTP): https://mcp.socialtoai.com/mcp · Auth: API key; OAuth sign-in for ChatGPT and Claude's apps |
| No key needed for | capabilities, find, OpenAPI |
| Price | $10 = 3,000 credits · $50 = 20,000 · $200 = 100,000 · any amount from $10 to $2,000 |
| Per call | most calls cost 2 credits (range 1–24); from $0.002 per call |
| Free | 100 credits on sign-up, no card. Credits never expire. No subscription. No refunds. |
| Charged | successful calls, including a search that ran and found nothing. Not charged: failed calls. |
| Limits | 1 request per second per key; 5 per second after the first purchase |
| Payment | card or Alipay, priced in USD |
| Data | content and account information publicly visible on the platform; commenters are anonymised |
| Updated | 2026-10-17 · price version pv_e5a1c68e5861 |

## What this is

One Markdown skill file ([`plugins/socialtoai/skills/socialtoai/SKILL.md`](plugins/socialtoai/skills/socialtoai/SKILL.md)) that tells your AI when to use SocialToAI, how to write each call, what it costs in credits and what to do when a call fails. It is generated from the platforms, calls and prices offered now, and one file covers every platform. This repository is also a Claude Code plugin marketplace: the plugin brings the MCP configuration and the skill file, and you provide the key.

## Install

### As a Claude Code plugin

```bash
export SOCIALTOAI_KEY="<YOUR_API_KEY>"

# in Claude Code
/plugin marketplace add socialtoai/socialtoai-skills
/plugin install socialtoai@socialtoai
```

The plugin reads the key from the environment variable `SOCIALTOAI_KEY`; no file holds it. Create a key in the [console](https://socialtoai.com/sign-in/?utm_source=github&utm_medium=repository).

### The skill file alone

```bash
mkdir -p ~/.claude/skills/socialtoai && \
  curl -fsSL https://socialtoai.com/skills/socialtoai/SKILL.md -o ~/.claude/skills/socialtoai/SKILL.md
```

How other AI clients connect to the MCP server is in https://github.com/socialtoai/socialtoai-mcp .

## Recorded examples

Questions that were run on the live system, with the names of ordinary users removed.

### What do people complain about with standing desks on Reddit and X?

- Searched Reddit “standing desk”: 7 posts · 2 credits
- Searched X “standing desk”: 11 posts · 2 credits
- Ran Comment analysis on Reddit comments under the 3 most-discussed threads: 173 comments · 84 credits

I searched both, then read 173 comments under the 3 most-discussed Reddit threads. 55 of the 162 that could be judged complain about something; the complaints cluster here:

- **Back and neck pain** (12%): “Either position for 8 hours solid leaves my back hurting.” ([source](https://www.reddit.com/r/BuyItForLife/comments/1ntedtv/do_standing_desks_actually_help_or_are_they/ngv5bws/))
- **Forgetting to switch between sitting and standing** (11%): “I forget I have it most of the time...” ([source](https://www.reddit.com/r/BuyItForLife/comments/1ntedtv/do_standing_desks_actually_help_or_are_they/ngt2t43/))
- **Sore feet from standing** (8%): “My feet do get tired by the end of the day it’s better than the back pain.” ([source](https://www.reddit.com/r/WFH/comments/1q1ia5q/i_bought_an_expensive_standing_desk_6_months_ago/nx6mz78/))

Replay · recorded 2026-10-18, 3 requests, 88 credits ($0.29)

### What home coffee content is taking off on TikTok and YouTube this week?

- Ran Viral finder on TikTok “home coffee”, last 7 days: 59 videos · 36 credits
- Ran Viral finder on YouTube “home coffee”, last 7 days: 57 videos · 24 credits

From 116 videos posted in the last 7 days (109 with a format the analysis could name), 15 took off (3 times the usual or more). The formats that took off most, each with its share of all the videos:

- **How-to** (24%): “October made me do it. 👻 Marshmallow Iced Latte Ingredients • 1 giant marshmallow” ([source](https://www.tiktok.com/@probablymultitasking/video/7695837117548612878))
- **Showcase** (25%): “Setting up my home coffee bar (for now hehe) ☕️🧸🤎🕯️ what do we think?!” ([source](https://www.tiktok.com/@dr.reemabassoumi/video/7695457439486971149))
- **Story** (20%): “I’ve been drinking mold for months.. PSA ALL AT HOME COFFEE MAKERS!” ([source](https://www.tiktok.com/@godblessthismommess/video/7697482627208498446))

Replay · recorded 2026-10-18, 2 requests, 60 credits ($0.2)

### What are people on Xiaohongshu saying about camping coffee?

- Ran Brand buzz on Xiaohongshu “露营咖啡”, last 90 days: 13 notes · 36 credits

8 of the 13 posts found are about it: 100% positive, 0% neutral, 0% negative. What they mention most:

- **Features** (38%): “泰摩手冲套装，户外也能稳定萃取” ([source](https://www.xiaohongshu.com/discovery/item/6ace5030000000000202b50a?xsec_token=YBG8sJk5ubaOiy4IR4aWFju_M8woOWi5f596-EyQu89_I%3D&xsec_source=app_share))
- **Ease of use** (25%): “意外比想象中方便。 撕开直接倒进水或牛奶里，冷水大约3秒就能化开” ([source](https://www.xiaohongshu.com/discovery/item/6a7166a8000000002500db01?xsec_token=YBPlj8LOiespGe8OC5mJrELhKzAcNDnW_YlU9aDOcRrL0%3D&xsec_source=app_share))
- **Quality** (13%): “亲手萃取的温柔质感 是成年人超治愈的低成本快乐” ([source](https://www.xiaohongshu.com/discovery/item/6a5f63d40000000001033a6e?xsec_token=YB4BbvhOU2v5iwKzbmgNXN3JuvanMCovT7SnEUZ4w3TH0%3D&xsec_source=app_share))

Replay · recorded 2026-10-18, 1 request, 36 credits ($0.12)

## Links

- Site: https://socialtoai.com/?utm_source=github&utm_medium=repository
- Connect your AI client: https://socialtoai.com/mcp/?utm_source=github&utm_medium=repository
- Pricing: https://socialtoai.com/pricing/?utm_source=github&utm_medium=repository
- Documentation: https://socialtoai.com/docs/?utm_source=github&utm_medium=repository
- Status: https://socialtoai.com/status/?utm_source=github&utm_medium=repository
- Changelog: https://socialtoai.com/changelog/?utm_source=github&utm_medium=repository
- The other repository: https://github.com/socialtoai/socialtoai-mcp
- Support: support@socialtoai.com
