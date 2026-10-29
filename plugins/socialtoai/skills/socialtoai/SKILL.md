---
name: socialtoai
description: "Read publicly visible social media content (posts, comments, profiles, trends) on TikTok, Instagram, X (Twitter), Reddit, YouTube, Facebook, LinkedIn, Threads, Telegram, Pinterest, Xiaohongshu (RedNote), Douyin, Weibo, WeChat Articles, Bilibili, Zhihu, Kuaishou, WeChat Channels, Meta Ad Library, Google Ads Transparency through the SocialToAI MCP server or HTTP API. Use it when the user asks what people say or post on these platforms, or wants a post, its comments, an account or a trending list. 需要读取社交媒体上公开可见的帖子、评论、账号或热榜时使用。"
---

# SocialToAI

SocialToAI is an API and MCP server that lets AI tools read publicly visible social media content (posts, comments, profiles and trends) from 18 platforms, including TikTok, Instagram, X (Twitter), Reddit, YouTube, Xiaohongshu (RedNote), Douyin, Weibo. It is billed in prepaid credits, and failed calls are free.

## Connect

- MCP (Streamable HTTP): `https://mcp.socialtoai.com/mcp`, with the header `Authorization: Bearer $SOCIALTOAI_API_KEY`.
- HTTP: `POST https://api.socialtoai.com/v1/<action>` with a JSON body and the same header.
- The key is read from the environment variable `SOCIALTOAI_API_KEY`. Never print a key, and never write one into a file, a command or an address.
- If the MCP tools are present, use them. Otherwise call the HTTP API.

## Actions

Every action takes `platform` and the parameters of that platform, and answers in the same format. `Price key` is what the call is billed as.

### search

Find posts or accounts by keyword. `POST https://api.socialtoai.com/v1/search`

| Platform | Price key | Credits | Required | Optional |
| --- | --- | --- | --- | --- |
| tiktok (type=user) | `tiktok.search:user` | 2 | query | - |
| tiktok | `tiktok.search` | 2 | query | sort, published_within |
| instagram (type=user) | `instagram.search:user` | 3 | query | - |
| x | `x.search` | 2 | query | sort |
| x (sort=latest) | `x.search:latest` | 2 | query | - |
| x (type=user) | `x.search:user` | 5 | query | - |
| reddit | `reddit.search` | 2 | query | sort, published_within |
| youtube | `youtube.search` | 2 | query | sort, published_within |
| linkedin | `linkedin.search` | 2 | query | published_within |
| threads | `threads.search` | 2 | query | since, until |
| pinterest | `pinterest.search` | 2 | query | - |
| xiaohongshu | `xiaohongshu.search` | 12 | query | sort |
| xiaohongshu (type=user) | `xiaohongshu.search:user` | 12 | query | - |
| xiaohongshu (type=image) | `xiaohongshu.search:image` | 12 | query | - |
| douyin | `douyin.search` | 12 | query | sort, published_within |
| douyin (type=user) | `douyin.search:user` | 2 | query | - |
| weibo | `weibo.search` | 2 | query | - |
| weibo (type=user) | `weibo.search:user` | 2 | query | - |
| wechat | `wechat.search` | 12 | query | sort, published_within |
| bilibili | `bilibili.search` | 2 | query | sort |
| zhihu | `zhihu.search` | 2 | query | type, sort |
| zhihu (type=user) | `zhihu.search:user` | 2 | query | - |
| kuaishou | `kuaishou.search` | 12 | query | - |
| wechat_channels | `wechat_channels.search` | 12 | query | sort, published_within |

### trending

What is hot right now. `POST https://api.socialtoai.com/v1/trending`

| Platform | Price key | Credits | Required | Optional |
| --- | --- | --- | --- | --- |
| x | `x.trending` | 6 | - | board, region |
| reddit | `reddit.trending` | 2 | - | board |
| reddit (type=trends) | `reddit.trending:trends` | 2 | - | board |
| xiaohongshu | `xiaohongshu.trending` | 12 | - | board |
| douyin | `douyin.trending` | 2 | - | board |
| douyin (type=videos) | `douyin.trending:videos` | 2 | - | board |
| weibo | `weibo.trending` | 2 | - | board |
| bilibili | `bilibili.trending` | 2 | - | board |
| bilibili (type=videos) | `bilibili.trending:videos` | 2 | - | - |
| zhihu | `zhihu.trending` | 2 | - | board |
| kuaishou | `kuaishou.trending` | 2 | - | - |

### detail

One post: text and numbers. `POST https://api.socialtoai.com/v1/detail`

| Platform | Price key | Credits | Required | Optional |
| --- | --- | --- | --- | --- |
| tiktok | `tiktok.detail` | 2 | one of id / url | - |
| tiktok (include=transcript) | `tiktok.detail:transcript` | 2 | one of id / url | - |
| instagram | `instagram.detail` | 2 | one of id / url | - |
| instagram (include=transcript) | `instagram.detail:transcript` | 2 | one of id / url | - |
| x | `x.detail` | 1 | one of id / url | - |
| reddit | `reddit.detail` | 2 | one of id / url | - |
| reddit (include=transcript) | `reddit.detail:transcript` | 2 | one of id / url | - |
| youtube | `youtube.detail` | 2 | one of id / url | - |
| youtube (include=transcript) | `youtube.detail:transcript` | 2 | one of id / url | - |
| facebook | `facebook.detail` | 2 | url | - |
| linkedin | `linkedin.detail` | 2 | one of id / url | - |
| linkedin (include=transcript) | `linkedin.detail:transcript` | 2 | one of id / url | - |
| threads | `threads.detail` | 2 | one of id / url | - |
| telegram | `telegram.detail` | 2 | one of id / url | - |
| pinterest | `pinterest.detail` | 2 | one of id / url | - |
| xiaohongshu | `xiaohongshu.detail` | 12 | one of id / url | - |
| douyin | `douyin.detail` | 2 | one of id / url | - |
| weibo | `weibo.detail` | 2 | id | - |
| wechat | `wechat.detail` | 12 | url | - |
| bilibili | `bilibili.detail` | 2 | one of id / url | - |
| zhihu | `zhihu.detail` | 2 | one of id / url | - |
| zhihu (type=question) | `zhihu.detail:question` | 2 | one of id / url | - |
| zhihu (type=article) | `zhihu.detail:article` | 2 | one of id / url | - |
| zhihu (type=pin) | `zhihu.detail:pin` | 2 | one of id / url | - |
| kuaishou | `kuaishou.detail` | 2 | one of id / url | - |
| wechat_channels | `wechat_channels.detail` | 12 | id | - |

### comments

Comments under a post. `POST https://api.socialtoai.com/v1/comments`

| Platform | Price key | Credits | Required | Optional |
| --- | --- | --- | --- | --- |
| tiktok (reply_of) | `tiktok.comments:replies` | 2 | id, reply_of | - |
| tiktok | `tiktok.comments` | 2 | one of id / url | - |
| instagram (reply_of) | `instagram.comments:replies` | 2 | id, reply_of | - |
| instagram | `instagram.comments` | 2 | one of id / url | - |
| x | `x.comments` | 2 | id | - |
| reddit | `reddit.comments` | 2 | one of id / url | sort |
| youtube | `youtube.comments` | 2 | one of id / url | sort |
| youtube (reply_of) | `youtube.comments:replies` | 2 | reply_of | - |
| facebook | `facebook.comments` | 2 | id | - |
| xiaohongshu | `xiaohongshu.comments` | 12 | one of id / url | - |
| xiaohongshu (reply_of) | `xiaohongshu.comments:replies` | 12 | id, reply_of | - |
| douyin | `douyin.comments` | 2 | id | - |
| douyin (reply_of) | `douyin.comments:replies` | 2 | id, reply_of | - |
| weibo | `weibo.comments` | 2 | id | - |
| wechat | `wechat.comments` | 12 | url | - |
| bilibili | `bilibili.comments` | 2 | id | - |
| bilibili (reply_of) | `bilibili.comments:replies` | 2 | id, reply_of | - |
| zhihu | `zhihu.comments` | 2 | id | - |
| zhihu (reply_of) | `zhihu.comments:replies` | 2 | reply_of | - |
| kuaishou | `kuaishou.comments` | 2 | id | - |
| kuaishou (reply_of) | `kuaishou.comments:replies` | 2 | id, reply_of | - |
| wechat_channels | `wechat_channels.comments` | 12 | id | - |

### user_profile

One account: bio and counts. `POST https://api.socialtoai.com/v1/user_profile`

| Platform | Price key | Credits | Required | Optional |
| --- | --- | --- | --- | --- |
| tiktok | `tiktok.user_profile` | 2 | one of id / username | - |
| instagram | `instagram.user_profile` | 2 | username | - |
| x | `x.user_profile` | 1 | one of id / username | - |
| reddit | `reddit.user_profile` | 2 | username | - |
| youtube | `youtube.user_profile` | 2 | one of id / username | - |
| facebook | `facebook.user_profile` | 2 | one of id / username / url | - |
| linkedin | `linkedin.user_profile` | 2 | one of username / url | - |
| threads | `threads.user_profile` | 2 | username | - |
| telegram | `telegram.user_profile` | 2 | username | - |
| xiaohongshu | `xiaohongshu.user_profile` | 12 | one of id / url | - |
| douyin | `douyin.user_profile` | 2 | one of id / url | - |
| weibo | `weibo.user_profile` | 2 | id | - |
| wechat | `wechat.user_profile` | 12 | id | - |
| bilibili | `bilibili.user_profile` | 2 | id | - |
| zhihu | `zhihu.user_profile` | 2 | username | - |
| kuaishou | `kuaishou.user_profile` | 12 | id | - |
| wechat_channels | `wechat_channels.user_profile` | 12 | id | - |

### user_posts

Posts from one account. `POST https://api.socialtoai.com/v1/user_posts`

| Platform | Price key | Credits | Required | Optional |
| --- | --- | --- | --- | --- |
| tiktok | `tiktok.user_posts` | 2 | username | sort |
| instagram | `instagram.user_posts` | 2 | username | type |
| x | `x.user_posts` | 2 | username | tab |
| reddit | `reddit.user_posts` | 2 | username | - |
| facebook | `facebook.user_posts` | 2 | one of id / username / url | - |
| linkedin | `linkedin.user_posts` | 2 | one of username / url | - |
| threads | `threads.user_posts` | 2 | username | - |
| telegram | `telegram.user_posts` | 2 | username | - |
| xiaohongshu | `xiaohongshu.user_posts` | 12 | one of id / url | - |
| douyin | `douyin.user_posts` | 2 | id | - |
| wechat | `wechat.user_posts` | 12 | id | - |
| bilibili | `bilibili.user_posts` | 2 | id | - |
| zhihu | `zhihu.user_posts` | 2 | username | - |
| zhihu (type=answer) | `zhihu.user_posts:answers` | 2 | username | - |
| zhihu (type=pin) | `zhihu.user_posts:pins` | 2 | username | - |
| kuaishou | `kuaishou.user_posts` | 12 | id | - |
| wechat_channels | `wechat_channels.user_posts` | 12 | id | - |

## Platform-specific interfaces

`POST https://api.socialtoai.com/v1/call/{op}`. The op is the price key.

| Price key | Credits | Required | Optional |
| --- | --- | --- | --- |
| `tiktok.top_ad_detail` | 2 | id | - |
| `tiktok.top_ad_search` | 2 | query | region, window, sort |
| `tiktok.hashtag_videos` | 2 | id | - |
| `tiktok.product_reviews` | 2 | id | - |
| `tiktok.product_search` | 2 | query | - |
| `tiktok.seller_products` | 2 | id | - |
| `tiktok.product_detail` | 2 | id | - |
| `tiktok.ad_search` | 2 | query | - |
| `tiktok.ad_detail` | 2 | one of id / url | - |
| `tiktok.followers` | 2 | username | - |
| `instagram.hashtag_posts` | 2 | id | - |
| `x.community` | 1 | id | - |
| `x.community_posts` | 4 | id | - |
| `x.list_posts` | 2 | id | - |
| `x.article` | 2 | id | - |
| `x.quotes` | 4 | id | - |
| `x.thread` | 9 | id | - |
| `x.followers` | 12 | username | - |
| `x.following` | 12 | username | - |
| `x.mentions` | 4 | username | - |
| `x.community_members` | 5 | id | - |
| `x.list_followers` | 5 | id | - |
| `x.list_members` | 5 | id | - |
| `reddit.user_subreddits` | 2 | username | - |
| `reddit.subreddit` | 2 | id | - |
| `reddit.subreddit_posts` | 2 | id | sort |
| `youtube.community_posts` | 2 | one of id / username | - |
| `youtube.community_post` | 2 | one of id / url | - |
| `linkedin.ad_detail` | 2 | one of id / url | - |
| `linkedin.ad_search` | 2 | query | region |
| `xiaohongshu.product_search` | 12 | query | - |
| `xiaohongshu.product_detail` | 12 | id | - |
| `xiaohongshu.product_reviews` | 12 | id | - |
| `xiaohongshu.topic_notes` | 12 | id | - |
| `xiaohongshu.topic` | 12 | id | - |
| `douyin.kol_search` | 3 | query | - |
| `douyin.kol_profile` | 3 | one of id | - |
| `douyin.kol_audience` | 3 | id | - |
| `douyin.kol_performance` | 3 | id | window |
| `douyin.brand_radar` | 2 | brand, since, until | - |
| `douyin.account_history` | 2 | one of id | window |
| `douyin.video_stats` | 2 | id | - |
| `douyin.related_videos` | 2 | id | - |
| `douyin.hashtag_videos` | 2 | id | - |
| `douyin.keyword_audience` | 2 | keyword, since, until | - |
| `douyin.keyword_history` | 4 | since, until, one of keyword | - |
| `douyin.kol_rates` | 24 | id | - |
| `douyin.kol_videos` | 3 | id | - |
| `douyin.brand_history` | 2 | brand, since, until | - |
| `douyin.account_top_videos` | 2 | id, since, until | - |
| `douyin.account_audience` | 2 | id | - |
| `douyin.account_metrics` | 2 | id | - |
| `douyin.keyword_related` | 2 | keyword, until | - |
| `douyin.keyword_videos` | 2 | query | - |
| `douyin.index_topics` | 2 | - | board |
| `douyin.kol_keywords` | 2 | id | - |
| `douyin.kol_scores` | 5 | id | - |
| `douyin.kol_content_mix` | 3 | id | - |
| `douyin.marketing_calendar` | 3 | since, until | - |
| `weibo.followers` | 2 | id | - |
| `weibo.likers` | 2 | id | - |
| `wechat.article_stats` | 12 | url | - |
| `zhihu.question_answers` | 2 | one of id / url | - |
| `zhihu.column_articles` | 2 | id | - |
| `zhihu.followers` | 2 | username | - |
| `wechat_channels.collections` | 12 | id | - |
| `wechat_channels.collection_videos` | 12 | id | - |
| `meta.ad_search` | 2 | query | region, sort, type |
| `meta.advertiser_ads` | 2 | id | region, sort, type |
| `meta.advertiser_search` | 2 | query | - |
| `meta.ad_detail` | 2 | one of id / url | - |
| `google.advertiser_ads` | 2 | id | region, type |
| `google.advertiser_search` | 2 | query | region |
| `google.ad_detail` | 2 | one of id / url | - |

## MCP tools

- `search`: Search a platform for content. Read-only. Each line: what to pass, then its platforms, 2 credits a call unless numbered. A list of platforms is one call each. Failed calls cost 0. Need 100 items? Pass limit=100 (each page a call).
- `trending`: Read a platform's trending list. Read-only. Each line: what to pass, then its platforms, 2 credits a call unless numbered. A list of platforms is one call each. Failed calls cost 0. Need 100 items? Pass limit=100 (each page a call).
- `detail`: Get one piece of content by its id or link. Read-only. Each line: what to pass (a|b: either one), then its platforms, 2 credits a call unless numbered. A list of platforms, ids or links is one call each. Failed calls cost 0.
- `comments`: Read the comments under one piece of content. Read-only. Each line: what to pass (a|b: either one), then its platforms, 2 credits a call unless numbered. A list of platforms, ids or links is one call each. Failed calls cost 0. Need 100 items? Pass limit=100 (each page a call).
- `user_profile`: Get one account's public profile: name, bio, verification and follower counts. Read-only. Each line: what to pass (a|b: either one), then its platforms, 2 credits a call unless numbered. A list of platforms is one call each. Failed calls cost 0.
- `user_posts`: List what one account has published. Read-only. Each line: what to pass (a|b: either one), then its platforms, 2 credits a call unless numbered. A list of platforms is one call each. Failed calls cost 0. Need 100 items? Pass limit=100 (each page a call).
- `find`: Find what can be called by what it does, in plain words, English or Chinese: the matching actions and ops, best first, each with its parameters, credits per call and a call that works. Free. Asked about docs or code, it adds the docs links. Where the platform asked about does not offer it, not_offered says so and only the closest calls are listed: tell the user, never pass those off as what was asked for.
- `call`: Call one platform-specific capability by its op ("platform.name"): what the six actions do not cover. find finds an op by what it does; capabilities lists each with its parameters and its credits per call (1 to 24). Read-only. A failed call costs 0.
- `capabilities`: List what can be called now: each action per platform and each op, with its parameters, credits per call, page size, the fields it cannot give and a call that works. Free. The whole list is long: pass platform.
- `account`: Whose key or connected app this is and where it stands: plan (free or paid), credit balance, and today's spend, daily limit and room left of the connection and its account; what buying gets, with a purchase link needing no sign-in (repeat purchase.display). Free. Writing a script? for_scripts says how to get an API key.
- `brand_buzz`: What people say about a brand or product on each platform: the share of each attitude, what is mentioned most, and the posts with the most engagement, each with its source link. Runs on our side. A costly or long run quotes its price first.
- `comment_insights`: What the comments under your posts are about: the topics and their shares, the questions asked, who wants to buy and what is complained about, with the comments quoted. Runs on our side. A costly or long run quotes its price first.
- `find_creators`: Creators on one platform for a niche: their size, their recent posts, and how well each fits what you asked for, with the reasons. Runs on our side. A costly or long run quotes its price first.
- `account_watch`: What a set of accounts published lately and which posts did clearly better than each account's usual. Runs on our side. A costly or long run quotes its price first.
- `creator_card`: One creator across platforms: the accounts found for the same person, with followers, posts, engagement and how strong the evidence is that each is theirs. Runs on our side. A costly or long run quotes its price first.
- `research`: Run one of these by its name, on our side. A costly or long run quotes its price first. Pass links whole, as given. On error, follow error.fix. Tell the user billing.display.
- `watch`: Watch for the user: a search, action, op or tool run again by us every day or week, delivering only what is new to email, webhooks, a Feishu/WeCom/Slack chat, an RSS feed and watch_news.
- `watch_news`: What the user's watches found that they have not been shown yet, newest first, with each watch, its time and status. Use it when the user asks what is new. Free. Pass id for one watch; what is shown is not shown again.

## Ready-made tools

- `brand_buzz`: What people say about a brand or product on each platform: the share of each attitude, what is mentioned most, and the posts with the most engagement, each with its source link.
- `comment_insights`: What the comments under your posts are about: the topics and their shares, the questions asked, who wants to buy and what is complained about, with the comments quoted.
- `account_watch`: What a set of accounts published lately and which posts did clearly better than each account's usual.
- `find_creators`: Creators on one platform for a niche: their size, their recent posts, and how well each fits what you asked for, with the reasons.
- `creator_card`: One creator across platforms: the accounts found for the same person, with followers, posts, engagement and how strong the evidence is that each is theirs.
- `batch_stats`: The numbers of up to 2,000 links to posts or account pages as they are now, and which links no longer work. No AI analysis.
- `viral_finder`: Posts on a subject that did clearly better than their authors usually do, on one platform.

## Rules

- Every answer carries `billing`: the credits this call cost and the balance. Tell the user what was spent when they ask, in credits.
- Charged: `ok`, `empty`. A search that ran and found nothing is `empty` and is charged. Everything else costs 0.
- When the user gives a budget, send `max_cost_credits`: a call that would cost more is refused for free, with the quote.
- A field that is `null` is one the platform does not give (see `unavailable`). Do not guess its value.
- Whoever wrote a comment is anonymous. Do not try to identify them.
- Send an `Idempotency-Key` header with every charged call over HTTP: a new one for each request, the same one when you retry it. If an answer was lost after a charge, the same request under the same key, or `GET /v1/results/{request_id}`, returns it for free.
- For the next page send `page.cursor` back unchanged as `cursor`; each page is its own call.
- Cite a source by its `url`. An item whose `url` is null has no link: say so, and never make one up.
- On an error read `error.fix`: it names the parameter, the allowed values or where to go. Correct the call once; do not repeat a call that failed the same way.
- After `timeout` the result is not known and nothing was charged. Do not retry by yourself; ask the user or send a new request only if the data is still needed.

## Error codes

| Code | HTTP | Retry |
| --- | --- | --- |
| `invalid_params` | 400 | no |
| `not_supported` | 400 | no |
| `unauthorized` | 401 | no |
| `insufficient_balance` | 402 | no |
| `max_cost_exceeded` | 402 | no |
| `plan_limit` | 403 | no |
| `key_scope_denied` | 403 | no |
| `not_found` | 200 / 404 | no |
| `idempotency_in_progress` | 409 | yes, after Retry-After |
| `handle_expired` | 410 | no |
| `idempotency_conflict` | 422 | no |
| `daily_limit_reached` | 429 | no |
| `free_failure_limit` | 429 | yes, after Retry-After |
| `rate_limited` | 429 | yes, after Retry-After |
| `internal_error` | 500 | yes, after Retry-After |
| `temporarily_unavailable` | 200 / 503 | yes, after Retry-After |
| `invalid_target` | 200 | no |
| `upstream_error` | 200 | depends (see retryable) |
| `timeout` | 200 | no |

## Facts

- Platforms (18): TikTok, Instagram, X (Twitter), Reddit, YouTube, Facebook, LinkedIn, Threads, Telegram, Pinterest, Xiaohongshu (RedNote), Douyin, Weibo, WeChat Articles, Bilibili, Zhihu, Kuaishou, WeChat Channels
- Ad libraries (2): Meta Ad Library, Google Ads Transparency
- Actions (6): search, trending, detail, comments, user_profile, user_posts, plus a catalog of platform-specific interfaces (find / call)
- Tools (7): Brand buzz, Comment analysis, Account watch, Find creators, Creator profile, Bulk link data, Viral finder
- API: https://api.socialtoai.com/v1 · MCP (Streamable HTTP): https://mcp.socialtoai.com/mcp · Auth: sign-in (OAuth) in ChatGPT, Claude, Claude Code, Codex and Cursor; an API key in a header for scripts and servers
- No key needed for: capabilities, find, OpenAPI
- Price: $10 = 3,000 credits · $50 = 20,000 · $200 = 100,000 · any amount from $10 to $2,000
- Per call: most calls cost 2 credits (range 1–24); from $0.002 per call
- Free: 100 credits on sign-up, no card. Credits never expire. No subscription. No refunds.
- Charged: successful calls, including a search that ran and found nothing. Not charged: failed calls.
- Limits: 5 requests per second per key; 20 per second after the first purchase
- Payment: card or Alipay, priced in USD
- Data: content and account information publicly visible on the platform; commenters are anonymised
- Updated: 2026-10-17 · price version pv_e5a1c68e5861
