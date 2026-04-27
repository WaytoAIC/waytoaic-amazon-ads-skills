# Soju Operating Boundaries

Use these rules across all Soju advertising skills.

## Source priority

- Course source: `/Users/wesleyzane/Downloads/soju广告课程/亚马逊中高阶广告课程-Soju-详细学习笔记.md`
- XMind maps are supporting references for ad traffic channels and SD layout.
- Do not copy the full course into skill files. Keep skill files procedural.

## Automation boundary

V1 can:

- gather MCP data
- parse reports
- calculate metrics
- classify problems
- draft action plans
- produce daily or weekly report text

V1 cannot:

- create campaigns
- change bids
- change budgets
- add negatives
- pause campaigns or ad groups
- change Amazon Ads backend state

Any bid, budget, negative, pause, or campaign-structure action must be labeled `approval_required=true`.

## Output discipline

Always separate:

- `数据事实`
- `Soju规则判断`
- `AI判断`
- `建议动作`

If evidence is weak, write `证据不足`. Do not turn missing data into a confident decision.

## Default fields

Default marketplace is `US` unless the user specifies another marketplace.

Common input fields:

- `marketplace`
- `asin_list`
- `parent_asin`
- `seed_keywords`
- `competitor_asins`
- `stage`
- `price`
- `gross_profit`
- `target_acos`
- `target_tacos`
- `report_files`
- `date_range`

Common output artifacts:

- `keyword_map.csv` or Markdown keyword tables
- `ad_diagnosis.md`
- `action_plan.csv` or Markdown action tables

## MCP boundaries

- SIF MCP owns keyword demand, keyword history, root trend, competition, ASIN keyword signals, advertising structure, and traffic/ad diagnosis where exposed.
- SellerSprite MCP supplements SPR and ASIN fundamentals: price, coupon, rating, reviews, category, variations, badges, listing quality, Google Trend when used by seasonality skill.
- Amazon Ads reports are the source of truth for actual spend, clicks, orders, sales, placement distribution, targeting performance, and search-term performance.
- Sorftime MCP is optional for product or market validation. If unavailable, continue and mark it unavailable.
