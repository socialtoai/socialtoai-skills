# SocialToAI 技能：要结果，不用拼接口

[English](README.md)

9 个技能，让 AI 读社交媒体上的公开内容，交回一份做好的结果。**只读公开内容，不发帖。** 不用你的平台账号，不会牵连你的账号。SocialToAI 团队发布。

## 你会拿到什么

2026-10-18 在线上真实跑的一次（[完整过程](https://socialtoai.com/zh/docs/guides/read-reddit-and-x-for-product-complaints/?utm_source=github&utm_medium=repo&utm_campaign=socialtoai-skills-20261106)）：

> **你：** Reddit 和 X 上大家怎么吐槽升降桌？
>
> **AI：** 读了 173 条评论，162 条能判断，55 条在吐槽。腰背和脖子疼 12%（20 条），忘记切换 11%（18 条），站久了脚疼 8%（13 条），每条都能点回原评论。
>
> **花费：** 88 积分，$0.29。

工作在我们这边做完，AI 不用花几万 token 自己拼调用。

## 安装

```bash
# 任何读 Agent Skills 的客户端：Claude Code、Codex、Cursor 等
npx skills add socialtoai/socialtoai-skills

# 只装一个
npx skills add socialtoai/socialtoai-skills --skill wechat-account-digest
```

```bash
# Claude Code 插件：连 MCP 连接一起装
/plugin marketplace add socialtoai/socialtoai-skills
/plugin install socialtoai@socialtoai
/mcp
```

不装插件时，第一次用会请你接入：一条命令或一个地址，然后登录。登录时自动建账户，送 **100 积分，不用绑卡**。中途积分用完，技能会把做完的部分交给你，给一个购买链接，买完从停下的地方继续。

## 技能清单

积分为 2026-11-05 查询。每个技能都写明费用，跑得多之前会先报价。

| 技能 | 你给它 | 你拿到 | 积分约 | 示例 |
| --- | --- | --- | --- | --- |
| `reddit-x-complaints` | 一个产品 | 抱怨分类和占比、期待、换用信号 | 88 | [录制](plugins/socialtoai/skills/reddit-x-complaints/examples/example.md) |
| `xiaohongshu-competitor-notes` | 竞品链接或关键词 | 跑赢平时的笔记、逐篇拆解、选题 | 126–186 | [录制](plugins/socialtoai/skills/xiaohongshu-competitor-notes/examples/example.md) |
| `douyin-comment-pain-points` | 视频链接或关键词 | 按占比排序的痛点，用评论者原话 | 62 | [录制](plugins/socialtoai/skills/douyin-comment-pain-points/examples/example.md) |
| `comment-purchase-drivers` | 讲产品的内容 | 为什么买、为什么犹豫、卖点草稿 | 62–132 | [录制](plugins/socialtoai/skills/comment-purchase-drivers/examples/example.md) |
| `weekly-brand-report` | 品牌和竞品 | 可以直接转发的周报，和上周对比 | 每周 36–348 | [录制](plugins/socialtoai/skills/weekly-brand-report/examples/example.md) |
| `overseas-reputation-check` | 品牌英文名 | 海外情绪、风险信号、英文原话和翻译 | 214 | [录制](plugins/socialtoai/skills/overseas-reputation-check/examples/example.md) |
| `creator-shortlist` | 领域和需求 | 初筛名单，含匹配理由和风险 | 139（抖音） | [录制](plugins/socialtoai/skills/creator-shortlist/examples/example.md) |
| `trending-topic-ideas` | 一个领域 | 10 个带证据的选题 | 118 | [录制](plugins/socialtoai/skills/trending-topic-ideas/examples/example.md) |
| `wechat-account-digest` | 一篇文章链接 | 公众号摘要，可选定时监控 | 72 | [仅格式示例，非录制](plugins/socialtoai/skills/wechat-account-digest/examples/example.md) |

标“录制”的示例来自真实录制，每个都写明哪些部分来自录制。`socialtoai` 是它们背后的参考技能，列出全部平台、调用和价格（18 个平台，216 个调用）。当前价格，不用 Key：https://api.socialtoai.com/v1/capabilities 。$10 = 3,000 积分，失败不扣。

## 接其他客户端

MCP 地址：`https://mcp.socialtoai.com/mcp`。各客户端步骤见 [socialtoai-mcp](https://github.com/socialtoai/socialtoai-mcp)。

支持：support@socialtoai.com。MIT 许可。SocialToAI 团队发布。
