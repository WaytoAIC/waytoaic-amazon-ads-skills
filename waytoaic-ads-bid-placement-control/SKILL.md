---
name: waytoaic-ads-bid-placement-control
description: Plan Soju-style Amazon bid and placement control. Use when the user asks about TOS, ROS, PP, Top of Search, Rest of Search, product pages, placement multiplier, 广告位加价, 固定竞价, 只降低, 提高和降低, 实际 bid, or how to control exposure distribution and CPC.
---

# WaytoAIC-Ads Bid Placement Control

This skill analyzes Amazon ad placement distribution and proposes bid, strategy, and placement multiplier changes. It outputs recommendations only.

## Read first

- `../shared/waytoaic-ads-operating-boundaries.md`
- `references/bid-placement-rules.md`
- `templates/bid-placement-output.md`

## Inputs

- Placement report or placement-level metrics
- campaign/ad group/targeting context
- current base bid
- current bidding strategy
- current TOS/ROS/PP placement multipliers
- target CPA, target ACOS, or gross profit if available

## Workflow

1. Calculate actual placement distribution from impressions, clicks, spend, sales, and orders.
2. Use the formula `actual bid = base bid x bidding strategy effect x placement multiplier`.
3. Classify the current bid level:
   - PP-level bid
   - normal ROS bid
   - high ROS / unstable TOS bid
   - stable TOS bid
4. Compare PP exposure against the Soju reference: PP impressions are often about 5 to 15 times `(TOS + ROS)` when no TOS boost is used.
5. Recommend whether to pursue TOS, ROS+PP, PP-only, ROS-only, or broad placement reduction.

## Output rules

- Every bid, strategy, or placement multiplier change must be `approval_required=true`.
- If placement data is missing, produce a diagnostic checklist instead of exact changes.
- Do not use TOS control for messy auto campaigns or mixed-target campaigns without warning that placement interpretation is distorted.
