# Example output · 示例输出

Built from a recorded run on the live service, published at https://socialtoai.com/docs/guides/analyse-douyin-comments/ (recorded 2026-10-18). Every number and quote is from that run. That run asked what commenters *ask*, so it surfaced questions more than complaints; a run of this skill sends a complaint-focused `focus` and reports the same way.

**Asked:** 抖音上热门咖啡视频的评论区，大家在问什么、卡在哪？

**Calls:** `comment_insights` (`targets`: 2 Douyin videos, `scale: "small"`): 36 comments read, 50 credits.

---

# 抖音评论痛点：热门咖啡视频 · 读了 36 条评论（28 条可判断）

**结论：** 28 条可判断的评论里 11 条在提问、7 条想买。最大的卡点是"不知道在哪买"：怎么买占 25%（7 条）。另有 21%（6 条）把视频里的糖看成了大米，说明画面没讲清用料。

| 痛点 / 话题 | 占比 | 典型原话 | 链接 |
| --- | --- | --- | --- |
| 不知道怎么买 | 25%（7 / 28） | “小程序怎么买啊” | [视频](https://www.douyin.com/video/7696845789318456571) |
| 看不懂用料（把糖看成大米） | 21%（6 / 28） | “我开始以为白花花的是大米呢……看到最后才明白是糖” | [视频](https://www.douyin.com/video/7696845789318456571) |
| 口味偏好（非痛点） | 18%（5 / 28） | “我最喜欢摩卡” | [视频](https://www.douyin.com/video/7697458024826604785) |

## 每个痛点

### 1. 不知道怎么买
- “小程序怎么买啊”（[视频](https://www.douyin.com/video/7696845789318456571)）
- **建议（非数据）：** 视频里挂购买入口，并在置顶评论里写清怎么买。

### 2. 看不懂用料
- “我开始以为白花花的是大米呢[捂脸]，看到最后才明白是糖[捂脸]”（[视频](https://www.douyin.com/video/7696845789318456571)）
- **建议（非数据）：** 前 3 秒加字幕标出原料。

## 评论里的提问

11 / 28 条在提问，最多的是购买方式（见上）。

## 花费

1 次请求，50 积分（$10 档约 $0.17）。
