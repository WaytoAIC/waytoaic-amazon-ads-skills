# Ad Report Diagnosis Rules

## Required metrics

Calculate when columns exist:

- `CTR = clicks / impressions`
- `CVR = orders / clicks`
- `CPC = spend / clicks`
- `CPA = spend / orders`
- `ACOS = spend / sales`
- `ROAS = sales / spend`
- `Spend share = row spend / total spend`
- `Sales share = row sales / total sales`
- `Ad order share = ad orders / total orders` when total orders are known

Use blanks, not zero, when denominator is zero.

## Report roles

| Report | Use |
| --- | --- |
| Search Term | what buyers actually searched and whether matching is clean |
| Targeting | bid/target performance and duplicated targeting |
| Placement | TOS/ROS/PP exposure and spend distribution |
| Advertised Product | ASIN-level ad efficiency and promoted SKU split |
| Purchased Product | whether spend is buying the intended product or leaking to other ASINs |

## Soju diagnosis actions

### 1. Repeated targeting

Check:

- same targeting and match type across multiple campaigns
- broad and phrase overlapping without purpose
- same exact keyword duplicated without budget/placement reason

Risk:

- budget fragmentation
- unclear winning structure
- self-competition and noisy diagnosis

### 2. Bid structure disorder

Ideal structure:

- exact > phrase = broad > auto = product targeting

Flag:

- exact and broad priced the same without reason
- product targeting bid higher than core keyword without strategic reason
- all match types using one bid

### 3. Main keyword funnel break

For high-spend search terms, expand:

- search term
- match type
- targeting keyword
- campaign
- ad group
- placement

Diagnose whether the keyword is:

- not getting impressions
- getting impressions but low CTR
- getting clicks but low CVR
- getting orders but no ranking/intervention value

### 4. Keyword-map blind spot

Compare report search terms against the keyword map:

- core words with no spend
- important roots only appearing accidentally
- bad roots with spend but no negative
- high-performing terms not moved into controlled structure

### 5. Positive intervention

Classify:

- `正向干预`: relevant traffic, acceptable CTR/CVR, orders or ranking value.
- `无效干预`: spend exists but no meaningful relevance, orders, or ranking effect.
- `反向干预`: low CTR/CVR or wrong traffic likely harms system expectation.

Do not assert ranking effect unless ranking or keyword evidence exists.

## Existing script reuse

When the user provides Sponsored Products Advertised Product report plus Targeting report and asks for targeting structure:

- prefer the existing `amazon-targeting-structure-report` skill/script
- then add Soju interpretation on top

Do not reimplement the same parsing path unless the existing script cannot run.
