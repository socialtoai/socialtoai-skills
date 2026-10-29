# Example output · 示例输出

Built from a recorded run on the live service, published at https://socialtoai.com/docs/guides/track-brand-mentions-on-douyin/ (recorded 2026-10-18, window 30 days). It shows the Douyin section of a report; a run of this skill uses `window: "7d"`, adds the other platforms and competitors in the same shape, and compares with last week. Numbers and quotes are from that run.

**Asked:** 瑞幸咖啡最近在抖音上口碑怎么样？

**Calls:** `brand_buzz` (`brand: "瑞幸咖啡"`, `about: "连锁咖啡品牌"`, `platforms: ["douyin"]`, `window: "30d"`, `scale: "small"`): 7 videos, 60 credits.

---

# 瑞幸咖啡 品牌报告 · 抖音 · 近 30 天（录制于 2026-10-18）

**一句话：** 读到的 7 条视频都在讲瑞幸，86% 正面、14% 中性、0% 负面；讨论集中在价格（43%），其次是新品设计和"在哪能买到"。与上周相比：**无上周报告**。

| 平台 | 相关 / 读到 | 正面 | 中性 | 负面 | 提到最多 |
| --- | --- | --- | --- | --- | --- |
| 抖音 | 7 / 7 | 86% | 14% | 0% | 价格（43%，3 条） |
| 小红书、微博 | **not in this run** | | | | |

## 本周最受关注的内容

1. **价格**（43%，3 条）：“0.01喝瑞幸教程”（[视频](https://www.douyin.com/video/7692360995854888356)）
2. **设计**（29%，2 条）：“高蛋白莓果酸奶饮，一杯约含20g蛋白质……代餐抗饿。”（[视频](https://www.douyin.com/video/7690305595958227443)）
3. **在哪买**（29%，2 条）：“也是在镇上喝上细糠了”（[视频](https://www.douyin.com/video/7696830697339897573)）

## 竞品对比

**not in this run**（真实运行时 `compare_with` 最多加 2 个竞品，同一口径计算）。

## 需要留意

样本只有 7 条，负面为 0；价格话题以"薅羊毛"教程为主，属于促销讨论而非投诉。

## 下周建议（建议，非数据）

- 读一下"0.01 喝瑞幸"这类视频的评论，看用户是在学方法还是在质疑活动。

## 花费

1 次请求，60 积分（$10 档约 $0.20）。
