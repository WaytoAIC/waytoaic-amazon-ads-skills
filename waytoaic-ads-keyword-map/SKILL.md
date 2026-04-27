---
name: waytoaic-ads-keyword-map
description: Build Soju-style Amazon keyword maps for launch and ad structure planning. Use when the user asks for 准流量词表, 全流量词表, 否词池, 词根分层, 竞品 ASIN 流量词, 自然词/广告词结构, PPC bid, keyword map, keyword launch plan, or Soju 广告课程 keyword workflow using SIF MCP plus SellerSprite MCP.
---

# WaytoAIC-Ads Keyword Map

This skill turns Soju's keyword research workflow into an operator-ready keyword map:

- 准流量词表
- 全流量词表
- 否词池
- 词根分层
- 主推词 / 辅助词 / 观察词 / 否定词
- 下一步广告结构建议

## Non-negotiable data ownership

Use these source boundaries exactly. Do not swap sources silently.

| Data needed | Primary source | Rule |
| --- | --- | --- |
| Competitor ASIN traffic keywords | SIF MCP | SIF owns this field. Do not use SellerSprite as a substitute unless the user explicitly approves a fallback. |
| Natural / ad keyword structure | SIF MCP | SIF owns natural vs ad structure and keyword traffic contribution. |
| PPC bid reference | SIF MCP | SIF owns PPC bid reference for this skill. |
| Keyword demand, history, root trend, competition | SIF MCP | Use SIF keyword tools for whether a keyword is worth attacking. |
| Keyword SPR | SellerSprite MCP | SellerSprite only supplements SPR or equivalent keyword ranking signal. |
| ASIN basic details | SellerSprite MCP | Use for price, coupon, rating, reviews, category, variations, badges, listing quality, and baseline competitiveness. |
| Market / product validation | Sorftime MCP | Optional enhancement only. If unavailable, write `Sorftime market validation unavailable` and continue. |

If a required SIF tool is not exposed in the current session, keep the field empty with `SIF capability not available in current MCP surface`; do not fill it from SellerSprite unless the user asks for an emergency fallback.

## Inputs

Minimum useful input:

- `marketplace`, default `US`
- 3 or more competitor ASINs, or 1 ASIN plus seed keywords

Optional but recommended:

- own ASIN or parent ASIN
- seed keywords
- target launch stage: `pre-launch`, `test`, `scale`, `stable`, or `shrink`
- gross profit, target CPA, target ACOS, or target TACOS
- known bad roots, protected brand terms, and words that must not be negated

## MCP workflow

1. Identify inputs and normalize marketplace.
2. Use SIF first:
   - competitor ASIN traffic keywords when an ASIN signal tool is available
   - natural / ad keyword structure when available
   - PPC bid reference when available
   - `market_get_keyword_demand` for keyword demand
   - `market_get_keyword_history` for keyword lifecycle
   - `market_get_keyword_root_trend` for root trends
   - `market_get_keyword_competition` for competition and rank evolution
3. Use SellerSprite only after SIF:
   - ASIN detail or detail with coupon trend for competitor competitiveness
   - keyword SPR or equivalent SellerSprite ranking signal when available
4. Treat Sorftime as optional:
   - use only for market/product validation if already authorized and relevant
   - if it returns authentication failure, note that it is unavailable and continue
5. Classify keywords using `references/waytoaic-ads-keyword-rules.md`.
6. Format the answer using `templates/keyword-map-output.md`.

## Output rules

- Output Chinese-first Markdown.
- Always separate `数据事实`, `Soju规则判断`, and `建议动作`.
- Always include source columns: `SIF`, `SellerSprite`, `Manual`, or `Unavailable`.
- Do not recommend direct backend changes as already executed. Output action suggestions only.
- Mark high-risk actions as `需人工确认`: adding phrase negatives, blocking brand terms, attacking expensive top words, or launching high-budget exact campaigns.
- For weak evidence, write `证据不足`, not a confident recommendation.

## When to read references

Read `references/waytoaic-ads-keyword-rules.md` before classification or recommendation.

Use `templates/keyword-map-output.md` when producing the final report.
