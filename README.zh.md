# SocialToAI 技能文件

[English](README.md)

SocialToAI 是一个让 AI 工具读取社交媒体上公开可见内容（帖子、评论、账号、热榜）的 API 和 MCP 服务，覆盖 TikTok、Instagram、X、Reddit、YouTube、小红书、抖音、微博 等 18 个平台。按预付积分计费，失败不扣。

## 事实

| 事实 | |
| --- | --- |
| 平台（18 个） | TikTok、Instagram、X、Reddit、YouTube、Facebook、LinkedIn、Threads、Telegram、Pinterest、小红书、抖音、微博、公众号、B 站、知乎、快手、视频号 |
| 广告库（2 个） | Meta 广告库、Google 广告透明度中心 |
| 动作（6 个） | search、trending、detail、comments、user_profile、user_posts，另有平台独有接口目录（find / call） |
| 工具（7 个） | 品牌口碑、评论分析、账号监测、找达人、达人档案、批量链接数据、爆款发现 |
| API | https://api.socialtoai.com/v1 · MCP（Streamable HTTP）：https://mcp.socialtoai.com/mcp · 认证：API Key；ChatGPT 和 Claude 应用用 OAuth 登录 |
| 不带 Key 可用 | capabilities、find、OpenAPI |
| 价格 | $10 = 3,000 积分 · $50 = 20,000 · $200 = 100,000 · $10 到 $2,000 的任意整数金额 |
| 每次调用 | 多数调用 2 积分（范围 1–24）；低至每次 $0.002 |
| 免费 | 注册送 100 积分、不用绑卡；积分不过期、不订阅、不退款。 |
| 计费 | 成功的调用扣费，搜索正常但没搜到照扣；失败不扣。 |
| 限制 | 每把 Key 每秒 1 次，首次购买后每秒 5 次 |
| 支付 | 银行卡或支付宝，以美元计价 |
| 数据 | 平台上公开可见的内容和账号信息；评论者一律匿名 |
| 更新 | 2026-10-17 · 价格版本 pv_e5a1c68e5861 |

## 这是什么

一个 Markdown 技能文件（[`plugins/socialtoai/skills/socialtoai/SKILL.md`](plugins/socialtoai/skills/socialtoai/SKILL.md)）：让你的 AI 知道什么时候该用 SocialToAI、每个调用怎么写、要花多少积分、出错了怎么办。它由当前开放的平台、调用和价格生成，一个文件覆盖全部平台。这个仓库同时是一个 Claude Code 插件市场：装上插件，就带上 MCP 配置和这个技能文件，Key 由你自己提供。

## 安装

### 作为 Claude Code 插件

```bash
# in Claude Code
/plugin marketplace add socialtoai/socialtoai-skills
/plugin install socialtoai@socialtoai
/mcp
```

装好后在 `/mcp` 里选 socialtoai，浏览器会打开登录页，用邮箱验证码登录并点「允许」即可，不用 Key，任何文件里也没有 Key。

### 只要技能文件

```bash
mkdir -p ~/.claude/skills/socialtoai && \
  curl -fsSL https://socialtoai.com/skills/socialtoai/SKILL.md -o ~/.claude/skills/socialtoai/SKILL.md
```

其他 AI 客户端怎么接入 MCP 服务，见 https://github.com/socialtoai/socialtoai-mcp 。

## 录制的示例

下面是在线上系统里真实运行过的问题，去掉了普通用户的名字。

### Reddit 和 X 上，大家对升降桌有哪些不满？

- Reddit 搜索 “standing desk”: 7 帖 · 2 积分
- X 搜索 “standing desk”: 11 帖 · 2 积分
- Reddit 评论分析 讨论最多的 3 帖的评论: 173 条评论 · 84 积分

两边都搜了，再读了 Reddit 上讨论最多的 3 帖下的 173 条评论。能判断的 162 条里有 55 条在抱怨，集中在这几点：

- **腰背和脖子疼** (12%): “Either position for 8 hours solid leaves my back hurting.” ([来源](https://www.reddit.com/r/BuyItForLife/comments/1ntedtv/do_standing_desks_actually_help_or_are_they/ngv5bws/))
- **忘了在坐和站之间切换** (11%): “I forget I have it most of the time...” ([来源](https://www.reddit.com/r/BuyItForLife/comments/1ntedtv/do_standing_desks_actually_help_or_are_they/ngt2t43/))
- **站久了脚疼** (8%): “My feet do get tired by the end of the day it’s better than the back pain.” ([来源](https://www.reddit.com/r/WFH/comments/1q1ia5q/i_bought_an_expensive_standing_desk_6_months_ago/nx6mz78/))

回放 · 录制于 2026-10-18，3 次请求，88 积分 ($0.29)

### 这周 TikTok 和 YouTube 上，家用咖啡什么内容在火？

- TikTok 爆款发现 “home coffee”，近 7 天: 59 条视频 · 36 积分
- YouTube 爆款发现 “home coffee”，近 7 天: 57 条视频 · 24 积分

近 7 天的 116 条视频里（能判断形式的 109 条），15 条起量（达到平时的 3 倍以上）。起量最多的几种形式，占比是占全部视频的比例：

- **教程** (24%): “October made me do it. 👻 Marshmallow Iced Latte Ingredients • 1 giant marshmallow” ([来源](https://www.tiktok.com/@probablymultitasking/video/7695837117548612878))
- **展示** (25%): “Setting up my home coffee bar (for now hehe) ☕️🧸🤎🕯️ what do we think?!” ([来源](https://www.tiktok.com/@dr.reemabassoumi/video/7695457439486971149))
- **故事** (20%): “I’ve been drinking mold for months.. PSA ALL AT HOME COFFEE MAKERS!” ([来源](https://www.tiktok.com/@godblessthismommess/video/7697482627208498446))

回放 · 录制于 2026-10-18，2 次请求，60 积分 ($0.2)

### 小红书上大家怎么聊露营咖啡？

- 小红书 品牌口碑 “露营咖啡”，近 90 天: 13 篇笔记 · 36 积分

找到的 13 条里有 8 条确实在说它：正面 100%，中性 0%，负面 0%。提到最多的是：

- **功能** (38%): “泰摩手冲套装，户外也能稳定萃取” ([来源](https://www.xiaohongshu.com/discovery/item/6ace5030000000000202b50a?xsec_token=YBG8sJk5ubaOiy4IR4aWFju_M8woOWi5f596-EyQu89_I%3D&xsec_source=app_share))
- **易用性** (25%): “意外比想象中方便。 撕开直接倒进水或牛奶里，冷水大约3秒就能化开” ([来源](https://www.xiaohongshu.com/discovery/item/6a7166a8000000002500db01?xsec_token=YBPlj8LOiespGe8OC5mJrELhKzAcNDnW_YlU9aDOcRrL0%3D&xsec_source=app_share))
- **质量** (13%): “亲手萃取的温柔质感 是成年人超治愈的低成本快乐” ([来源](https://www.xiaohongshu.com/discovery/item/6a5f63d40000000001033a6e?xsec_token=YB4BbvhOU2v5iwKzbmgNXN3JuvanMCovT7SnEUZ4w3TH0%3D&xsec_source=app_share))

回放 · 录制于 2026-10-18，1 次请求，36 积分 ($0.12)

## 链接

- 官网：https://socialtoai.com/zh/?utm_source=github&utm_medium=repository
- 接入你的 AI 客户端：https://socialtoai.com/zh/mcp/?utm_source=github&utm_medium=repository
- 价格：https://socialtoai.com/zh/pricing/?utm_source=github&utm_medium=repository
- 文档：https://socialtoai.com/zh/docs/?utm_source=github&utm_medium=repository
- 运行状态：https://socialtoai.com/zh/status/?utm_source=github&utm_medium=repository
- 更新日志：https://socialtoai.com/zh/changelog/?utm_source=github&utm_medium=repository
- 另一个仓库：https://github.com/socialtoai/socialtoai-mcp
- 支持：support@socialtoai.com
