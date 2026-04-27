# Soju Keyword Rules

This reference captures the keyword rules needed by `waytoaic-ads-keyword-map`. It is not a full copy of the course notes; it is the operational rule layer.

## Goal

The keyword map answers four questions before ads are built:

1. Which traffic words are worth positive intervention?
2. Which roots and keywords are too broad, wrong, or unwinnable?
3. Which keywords should be used for testing, scaling, ranking, or observation?
4. Which keywords should be excluded before they damage CTR, CVR, GMV, or keyword weight?

## Keyword tables

### 准流量词表

Purpose:

- Select attack direction.
- Choose main launch words and strong related words.
- Judge market size and promotion difficulty.
- Avoid spending on traffic that cannot create positive intervention.

Typical inclusion:

- Strongly relevant keywords from competitor ASINs.
- Keywords where target product has a credible CTR/CVR chance.
- Keywords with SIF evidence of demand and non-hopeless competition.
- Keywords with clear root alignment to the product.

Decision labels:

- `主推词`: strong relevance, meaningful demand, acceptable competition, and worth ranking or occupying.
- `辅助词`: relevant but smaller, weaker, or better for secondary structure.
- `观察词`: relevant but evidence is incomplete, bid is too high, or intent is mixed.
- `暂不打`: relevant in theory but current product cannot create positive intervention.

### 全流量词表

Purpose:

- Predict the maximum search term range that broad, phrase, auto, and product targeting may trigger.
- Design campaign structure before spend happens.
- Prepare negatives and separation rules in advance.

Typical inclusion:

- Strong related words.
- Weak related words.
- Upper-level category words.
- Attribute, use-case, audience, material, size, color, bundle, and accessory roots.
- Search terms likely to be triggered by broad match or auto campaigns.

Do not treat every full-traffic keyword as a launch target. Many are only there to control structure and prevent waste.

### 否词池

Purpose:

- Protect CTR.
- Protect CVR.
- Protect GMV quality.
- Prevent wrong traffic from weakening system expectation.

Typical negative candidates:

- Wrong product roots.
- Imprecise roots that consistently pull irrelevant traffic.
- Spend without orders after enough clicks.
- Orders with no strategic value.
- Competitor brand terms that cannot be beaten.
- High-spend terms that do not improve ranking or natural position.

Negative type:

- `精准否定`: use for a specific bad search term, upper-level word, or isolated irrelevant query.
- `词组否定`: use for wrong roots or consistently bad root clusters.
- `待定`: use for neutral words, competitor brands, or terms with mixed intent until more evidence is available.

Never phrase-negative a root if it can block valid future long-tail traffic unless the evidence is strong.

## Root classification

Classify each keyword by root level:

| Level | Definition | Example pattern | Operational meaning |
| --- | --- | --- | --- |
| 上位词 | Shorter and broader than the core product word | `mat`, `towel`, `headset` | Usually high traffic, high ambiguity, high risk. |
| 一级词 | Core product word, usually `A + B` | `beach towel` | Main launch and ranking candidate if product-market fit is strong. |
| 二级词 | Core word plus one non-core modifier | `oversized beach towel` | Good for testing and stable scaling. |
| 三级词 | Core word plus two or more modifiers | `oversized microfiber beach towel` | Lower CPC, clearer intent, useful for bottom-up launches. |
| 非核心词 | Attribute, audience, material, scenario, or modifier | `waterproof`, `thick`, `for women` | Use for root extension and negative review. |

When a keyword has multiple possible core roots, pick the root that best reflects buyer intent, then record the ambiguity.

## 准词 vs 泛词

Use both data and semantic judgment.

准词 characteristics:

- Product is clearly what the buyer expects.
- Competitor ASINs are similar to the target product.
- CTR/CVR can plausibly be positive.
- SIF demand exists and competition is not structurally impossible.
- SellerSprite ASIN details show the competitors are not unbeatable on price, rating, review volume, badges, or coupon.

泛词 characteristics:

- Intent includes multiple product types.
- Large traffic but broad buyer expectation.
- High risk of PP-heavy or low-conversion traffic.
- Useful for full-traffic map and negatives, not always for launch.

Course-style heuristic:

- High relevance/performance evidence means likely 准词.
- Mid evidence means likely 泛词 or auxiliary.
- Low evidence or wrong root means observation or negative.

## Broad match and auto boundaries

Broad match is buying a package of possible search terms, not only the bid keyword. Before using broad:

- Check full-traffic map.
- Identify wrong roots and imprecise roots.
- Decide which roots should be phrase-negative before launch.
- Separate broad campaigns if a root can consume budget and suppress smaller terms.

Auto campaigns can collect terms when:

- The product's core word is long-tail, accessory-like, or highly compositional.
- Close match can test relevant traffic cheaply.
- Pre-negatives protect obvious wrong roots.

Auto campaigns should not be left unmanaged. Use search term evidence to move good terms into manual structure and add bad terms to the negative pool.

## Flow concentration and promotion difficulty

High concentration:

- Few big keywords control most traffic.
- Top ad and natural positions are valuable.
- New products face high CPC and high intervention requirements.
- Use only when budget, conversion, and product competitiveness are strong.

Moderate dispersion:

- More attackable words.
- Better for new product launches.
- Requires wider structure and careful root grouping.

High dispersion:

- Many small words and inconsistent buyer names.
- Easier to win individual terms.
- Harder to create fast total volume.
- Requires long-tail scale and strong keyword organization.

## SIF decision layer

Use SIF to decide keyword value:

- Demand: Is there enough monthly demand or purchase signal?
- History: Is demand rising, stable, seasonal, or declining?
- Root trend: Is the root growing or weakening?
- Competition: Are top positions dominated, volatile, or realistically enterable?
- PPC bid: Is the expected click cost compatible with CPA and launch stage?
- Natural/ad structure: Is the keyword driven by organic strength, ads, or both?

If SIF evidence conflicts with semantic relevance, do not force a recommendation. Label the word `观察词` or `证据不足`.

## SellerSprite support layer

Use SellerSprite only for:

- Keyword SPR or equivalent keyword ranking signal.
- Competitor ASIN detail: price, coupon, rating, review count, category, variations, BSR/badges, listing quality.

Do not use SellerSprite traffic keyword, natural/ad split, or PPC bid as primary evidence inside this skill unless the user explicitly approves a fallback because SIF is unavailable.

## Classification matrix

| Condition | Keyword label | Action |
| --- | --- | --- |
| Strong relevance + demand + acceptable competition + affordable bid | 主推词 | Put into 准流量词表 and design ranking or launch structure. |
| Strong relevance + smaller demand or higher uncertainty | 辅助词 | Use for testing, long-tail scaling, or secondary campaigns. |
| Mixed intent + high demand + high competition | 观察词 | Keep in full map, test cautiously, avoid aggressive spend. |
| Wrong root or wrong buyer intent | 否定词 | Add to 否词池; choose exact or phrase negative by root risk. |
| Good orders but unclear root relationship | 待定词 | Keep monitored; do not negate until enough evidence exists. |
| High spend + no ranking lift + no positive intervention | 暂不打 | Stop scaling; consider bid down, budget down, negative, or structure split. |

## Final recommendation discipline

- Recommend ranking pushes only when there is both positive-intervention potential and enough budget.
- Recommend broad or auto only when negatives and root boundaries are defined.
- Recommend exact scaling only when CPA is acceptable, ranking value is clear, or the keyword is worth occupying.
- Recommend negatives carefully; distinguish exact negative from phrase negative.
- If data is missing, write what is missing and what should be checked next.
