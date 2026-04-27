---
name: waytoaic-ads-profit-tacos-planner
description: Build Soju-style CPA, ACOS, TACOS, profit, budget, and ad/natural order share plans. Use when the user asks for CPA, ACOS, ROAS, TACOS, 毛利, 利润倒推, 广告单占比, 自然单目标, 目标销量, budget cap, investment ads, profitable ads, or whether ads should scale or shrink from a profit view.
---

# WaytoAIC-Ads Profit TACOS Planner

This skill turns Soju's profit formulas into budget and order-share planning. It does not edit budgets directly.

## Read first

- `../shared/waytoaic-ads-operating-boundaries.md`
- `references/profit-tacos-rules.md`
- `templates/profit-tacos-output.md`

## Inputs

- price
- gross profit per unit
- CPC and CVR, or actual CPA
- target ACOS or target TACOS
- target total orders or sales
- current ad orders and natural orders if available

## Workflow

1. Calculate CPA, ACOS, ROAS, TACOS, and ad order share.
2. Classify ads:
   - profitable ad: `CPA < gross_profit`
   - investment ad: `CPA >= gross_profit`
3. Reverse-plan:
   - allowed ad spend
   - allowed ad orders
   - required natural orders
   - budget cap
   - shrink trigger
4. Decide whether the current structure is fit for scale, stable maintenance, or shrink.

## Output rules

- State formulas used.
- Mark budget changes as `approval_required=true`.
- If gross profit is missing, do not call an ad profitable; use CPA/ACOS scenarios instead.
