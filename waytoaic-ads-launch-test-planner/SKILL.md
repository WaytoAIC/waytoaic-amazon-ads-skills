---
name: waytoaic-ads-launch-test-planner
description: Build Soju-style Amazon launch and baseline bid test plans. Use when the user asks for 基准竞价测试, 新品测试, 放量前测试, 自动紧密, 手动广泛, 固定竞价, 预算 CPA 3-5 倍, CPC estimation, launch test campaign structure, or whether a new ASIN can create positive intervention.
---

# WaytoAIC-Ads Launch Test Planner

This skill turns Soju's baseline bid testing logic into a test campaign plan. It outputs structures and budgets only; it does not create Amazon Ads campaigns.

## Read first

- `../shared/waytoaic-ads-operating-boundaries.md`
- `references/launch-test-rules.md`
- `templates/launch-test-output.md`

## Inputs

Minimum useful input:

- marketplace, default `US`
- ASIN or product description
- seed keywords or output from `waytoaic-ads-keyword-map`
- price and gross profit if profit judgment is required

Recommended:

- target CPA or target ACOS
- competitor ASINs
- expected launch stage
- prior CPC/CVR if available

## Workflow

1. Use `waytoaic-ads-keyword-map` output if available; otherwise ask SIF for keyword demand, competition, and PPC bid reference.
2. Estimate baseline CPC and CPA from SIF PPC bid, expected CVR, and user profit parameters.
3. Build a low-risk test structure:
   - SP auto close match only
   - SP manual broad for 1 to 3 strong level-1 terms
   - fixed bidding by default
   - pre-negatives from the keyword map
4. Set daily budget guidance:
   - test budget usually equals estimated CPA times 3 to 5
   - if no CPA exists, state missing data and use CPC/click target as a temporary proxy
5. Define pass/fail rules for exposure, CTR, CVR, CPA, and positive intervention.

## Output rules

- Output a table of proposed test campaigns, ad groups, match type, bid logic, and budget.
- Mark every launch action as `approval_required=true`.
- If the product cannot plausibly create positive intervention, recommend postponing scale and list the blockers.
