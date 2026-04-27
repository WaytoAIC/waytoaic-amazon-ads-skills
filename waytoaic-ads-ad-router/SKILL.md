---
name: waytoaic-ads-ad-router
description: Route Soju-style Amazon advertising requests to the right Soju skill. Use when the user mentions Soju 广告课程, 亚马逊广告自动化, 新品准备, 竞价测试, 放量, 维稳, 缩量, 广告位, TACOS, 多变体, 季节性推广, or wants one entry point for keyword, report, bid, placement, launch, scale, profit, or seasonality decisions.
---

# WaytoAIC-Ads Ad Router

This is the entry skill for the Soju advertising skill suite. It decides which specialized skill should handle the request and combines results into an action plan.

## Read first

- `../shared/waytoaic-ads-operating-boundaries.md`
- `references/router-rules.md`
- `templates/router-output.md`

## Routing map

| User intent | Route to |
| --- | --- |
| 准流量词表, 全流量词表, 否词池, 词根分层 | `waytoaic-ads-keyword-map` |
| 基准竞价测试, 新品测试结构, 自动紧密, 手动广泛 | `waytoaic-ads-launch-test-planner` |
| 报表诊断, Search Term, Targeting, Placement, 重复投放, 盲区 | `waytoaic-ads-ad-report-diagnosis` |
| TOS, ROS, PP, 广告位加价, 固定竞价, 实际 bid | `waytoaic-ads-bid-placement-control` |
| 放量, 缩量, 拆活动, 加词, 合并活动, 降价, 关停 | `waytoaic-ads-scale-shrink-planner` |
| 多变体, 主推 SKU, 辅推 SKU, 父体, 测款 | `waytoaic-ads-variant-strategy` |
| CPA, ACOS, TACOS, 利润倒推, 广告单占比 | `waytoaic-ads-profit-tacos-planner` |
| 季节性, 节日性, 旺季, Google Trend, A-B-C-D-E | `waytoaic-ads-seasonality-planner` |

## Workflow

1. Identify the object: ASIN, parent ASIN, keyword, campaign, report file, product stage, or market.
2. Identify the stage: `pre-launch`, `test`, `scale`, `stable`, `shrink`, or `seasonal`.
3. Choose 1 to 3 skills only. Do not run the whole suite by default.
4. If reports are required but missing, state which report is missing and produce a partial plan.
5. Combine outputs into one Chinese action plan.

## Output rules

- Start with the selected route and why.
- Keep source boundaries explicit.
- Never state that backend changes were executed.
- Use `approval_required=true` for bid, budget, negative, pause, or campaign-creation actions.
