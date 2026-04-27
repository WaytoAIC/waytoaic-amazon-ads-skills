---
name: waytoaic-ads-scale-shrink-planner
description: Build Soju-style Amazon ad scale and shrink plans. Use when the user asks for 放量, 缩量, 拆活动, 加词, 长尾翻量, 精准翻量, 商品投放扩量, 合并活动, 降竞价, 降预算, 关停广告类型, protect core traffic, or create an action_plan.csv.
---

# WaytoAIC-Ads Scale Shrink Planner

This skill converts diagnosis into scale, stabilize, or shrink actions. It does not execute backend changes.

## Read first

- `../shared/waytoaic-ads-operating-boundaries.md`
- `references/scale-shrink-rules.md`
- `templates/scale-shrink-output.md`

## Inputs

- output from `waytoaic-ads-keyword-map`, `waytoaic-ads-ad-report-diagnosis`, or `waytoaic-ads-bid-placement-control`
- campaign/ad group/keyword/search-term metrics
- target CPA, target ACOS, or gross profit
- current stage: `scale`, `stable`, or `shrink`

## Workflow

1. Identify whether each traffic unit is profitable, investment-type, or waste.
2. For scale:
   - split high-performing words into dedicated structure
   - add level-1 or level-2 terms
   - add long-tail expansion
   - add product targeting only as auxiliary expansion
   - add ad types only when the role is clear
3. For shrink:
   - merge weak campaigns
   - reduce or remove weak match types
   - bid down high-CPA non-core targets
   - reduce budgets with redundant bid
   - close low-return ad types
4. Protect core traffic before shrinking.

## Output rules

- Every bid, budget, negative, pause, merge, or new-campaign recommendation must be `approval_required=true`.
- Do not shrink a high-ACOS target if it is a protected ranking target unless investment value is explicitly evaluated.
- Keep recommendations in priority order: P0, P1, P2.
