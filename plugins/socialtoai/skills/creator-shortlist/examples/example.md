# Example output · 示例输出

Built from a recorded run on the live service, published at https://socialtoai.com/docs/guides/find-creators-on-douyin/ (recorded 2026-10-18). The published run shows only totals, not the individual creators, so the table rows below are **not in this run**; a run of this skill lists each creator with their public handle and link.

**Asked:** 抖音上找家居收纳方向的达人，想做一次合作。

**Calls:** `find_creators` (`query: "家居收纳"`, `platform: "douyin"`, `scale: "small"`): 20 creators from the platform's own creator marketplace, 9 credits.

---

# 达人初筛：家居收纳 · 抖音

**一句话：** 从星图读到 20 位家居收纳达人，按需求判断 17 位（85%）高度匹配、3 位（15%）部分匹配；9 位（45%）粉丝在 10 万以上。

| # | 达人 | 粉丝 | 近期互动（比自己平时） | 匹配理由 | 风险 | 其他平台 | 链接 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1–10 | **not in this run** | | | | | | |

| 汇总 | 人数 | 占比 |
| --- | --- | --- |
| 高度匹配 | 17 / 20 | 85% |
| 部分匹配 | 3 / 20 | 15% |
| 粉丝 ≥ 10 万 | 9 / 20 | 45% |

## 下一步

- 对前 5 位跑 `creator_card` 看小红书、B 站有没有同一人的账号；
- 在星图里核对报价（`douyin.kol_rates`）和粉丝画像后再谈；合作内容要标"广告"或平台的合作标识。

## 花费

1 次请求，9 积分（$10 档约 $0.03）。
