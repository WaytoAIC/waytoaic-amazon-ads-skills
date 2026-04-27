---
name: waytoaic-ads-seasonality-planner
description: Plan Soju-style Amazon seasonal, holiday, and peak-season ad rhythm. Use when the user asks about 季节性推广, 节日性产品, 旺季, A-B-C-D-E, Google Trends, keyword seasonality, peak preparation, pre-season testing, high-season scaling, post-peak shrink, or clearance vs profit maximization.
---

# WaytoAIC-Ads Seasonality Planner

This skill maps seasonal demand into Soju's A-B-C-D-E promotion rhythm and outputs stage-specific ad actions.

## Read first

- `../shared/waytoaic-ads-operating-boundaries.md`
- `references/seasonality-rules.md`
- `templates/seasonality-output.md`

## Data ownership

- SellerSprite Google Trend: external trend validation.
- SIF keyword history/root trend: Amazon keyword lifecycle and root trend.
- SellerSprite ASIN prediction or other sales trend data: competitor/product seasonality when available.
- Sorftime market validation: optional only.

## Inputs

- core keyword or keyword roots
- ASIN or competitor ASINs
- marketplace, default `US`
- product type: strong seasonal, holiday, or peak-season uplift
- current date and planned inventory window if available

## Workflow

1. Determine whether demand is strong seasonal, holiday, or peak-season uplift.
2. Use trend evidence to locate A, B, C, D, and E when possible:
   - A: season starts
   - B: fast growth starts
   - C: peak stabilizes
   - D: fast decline starts
   - E: season ends
3. Map current date to the stage.
4. Output actions for new products and old products separately.
5. Decide whether the post-peak objective is clearance or profit maximization.

## Output rules

- Do not recommend starting serious promotion only at peak unless evidence supports it.
- Mark budget and bid changes as `approval_required=true`.
- If trend data is missing, output a trend-check plan and avoid exact date claims.
