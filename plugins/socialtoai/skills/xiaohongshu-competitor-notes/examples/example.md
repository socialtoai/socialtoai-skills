# Example output · 示例输出

Built from two recorded runs on the live service, published at https://socialtoai.com/docs/guides/find-viral-notes-on-xiaohongshu/ and https://socialtoai.com/docs/guides/read-xiaohongshu-notes-on-a-topic/ (both recorded 2026-10-18). Every number and quote below is from those runs. Parts the runs did not cover are marked **not in this run**; a real run of this skill fills them in.

**Asked:** 小红书上露营类笔记这个月哪些火了？顺便看看露营咖啡大家怎么说。

**Calls:** `research` → `viral_finder` (`query: "露营"`, `window: "30d"`, `scale: "small"`): 14 notes, 54 credits. `brand_buzz` (`brand: "露营咖啡"`, `window: "90d"`, `scale: "small"`): 13 notes, 36 credits.

---

# 小红书竞品笔记拆解：露营 · 近 30 天

**结论：** 14 篇露营笔记里只有 1 篇达到作者平时互动的 3 倍以上，是一条亲子搞笑日常，不是装备测评。故事类占 36%（5 篇）、展示类占 21%（3 篇），但这两类这次都没有一篇跑出 3 倍。露营咖啡相关的 13 篇里 8 篇真正在讲它，口碑全部正面，提到最多的是功能（38%）和方便（25%）。

| 笔记 | 形式 | 比作者平时 | 链接 |
| --- | --- | --- | --- |
| 孩子期盼已久的露营，终于安排上了 | 搞笑（Comedy） | ≥ 3 倍 | [原帖](https://www.xiaohongshu.com/discovery/item/6accc58f000000001803899c?xsec_token=YBrpZDYeMwvWxiZ3xP2aQnayx1a9OTzYNWdEgZtGCiVlY%3D&xsec_source=app_share) |

赞、藏、评的具体数字：**not in this run**（录制页只公开了倍数和形式分布）。

## 逐篇拆解

### 1. 孩子期盼已久的露营，终于安排上了
- **标题写法：** 情绪 + 期待落地（"期盼已久""终于"），不提装备。
- **形式：** 搞笑日常；正文带 #露营 #抽象 #猎奇 #母女搞笑日常。
- **评论区在问：** **not in this run**（这次没有读评论；真实运行会对这篇调 `comments`）。

## 露营咖啡：大家在说什么（`brand_buzz`）

8 / 13 篇在讲露营咖啡：正面 100%，中性 0%，负面 0%。

1. **功能**（38%，3 篇）：“泰摩手冲套装，户外也能稳定萃取”（[原帖](https://www.xiaohongshu.com/discovery/item/6ace5030000000000202b50a?xsec_token=YBG8sJk5ubaOiy4IR4aWFju_M8woOWi5f596-EyQu89_I%3D&xsec_source=app_share)）
2. **方便**（25%，2 篇）：“意外比想象中方便。撕开直接倒进水或牛奶里，冷水大约3秒就能化开”（[原帖](https://www.xiaohongshu.com/discovery/item/6a7166a8000000002500db01?xsec_token=YBPlj8LOiespGe8OC5mJrELhKzAcNDnW_YlU9aDOcRrL0%3D&xsec_source=app_share)）
3. **品质**（13%，1 篇）：“亲手萃取的温柔质感 是成年人超治愈的低成本快乐”（[原帖](https://www.xiaohongshu.com/discovery/item/6a5f63d40000000001033a6e?xsec_token=YB4BbvhOU2v5iwKzbmgNXN3JuvanMCovT7SnEUZ4w3TH0%3D&xsec_source=app_share)）

## 共同点

只有 1 篇跑出来，样本太小，不下结论；真实运行会按账号用 `account_watch` 读每个号约 20 篇，再比较。

## 可以借鉴的 3 个选题（建议，非数据）

1. 「带娃露营第一杯手冲」：沿用"期待落地"的情绪标题，咖啡只是道具。
2. 「露营咖啡 3 秒冲好」：直接用评论和笔记里的"方便"说法做标题。
3. 「户外也能稳定萃取？实测」：把"功能"这个讨论点做成对比测评。

## 花费

2 次请求，90 积分（$10 档约 $0.30）。
