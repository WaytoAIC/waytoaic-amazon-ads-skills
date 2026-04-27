---
name: waytoaic-ads-variant-strategy
description: Plan Soju-style Amazon multi-variation advertising strategy. Use when the user asks about 多变体, 父体, 子体, 主推 SKU, 辅推 SKU, 测款, 变体分工, 80/20 中性词分配, avoiding internal traffic cannibalization, or which child ASIN should carry ranking.
---

# WaytoAIC-Ads Variant Strategy

This skill plans parent-child variation advertising roles and testing order according to Soju's multi-variation rules.

## Read first

- `../shared/waytoaic-ads-operating-boundaries.md`
- `references/variant-rules.md`
- `templates/variant-output.md`

## Inputs

- parent ASIN and child ASINs
- variation attributes: size, color, pack, price, offer, rating, reviews
- keyword map or target keyword set
- sales/ad metrics by child ASIN if available

## Workflow

1. Identify whether the parent has one clear main child or multiple competing children.
2. Judge each child on price, conversion, review base, offer strength, and keyword relevance.
3. Assign roles:
   - main variation carries major neutral keyword traffic
   - secondary variations support specific attributes, higher ASP, or auxiliary paid positions
4. Design controlled tests:
   - same time window
   - same budget
   - same target words
   - fixed bid where possible
   - one child at a time when cannibalization risk is high
5. Produce main/secondary keyword allocation and risk controls.

## Output rules

- Do not recommend pushing all variations equally by default.
- Warn when multiple child ASINs are fighting the same keyword and weakening ranking concentration.
- Backend changes remain recommendations only and require approval.
