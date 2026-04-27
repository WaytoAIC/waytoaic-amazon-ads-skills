# Launch Test Rules

## Core principle

Testing is not "try and see"; it exists to get baseline values for later control:

- exposure threshold
- baseline CPC
- placement source
- CTR
- CVR
- CPA
- whether the product can create positive intervention

## Campaign test structure

Default test structure:

| Structure | Purpose | Default rule |
| --- | --- | --- |
| SP Auto Close Match | Test close relevant traffic and auto collection | fixed bidding, pre-negatives, close match only where possible |
| SP Manual Broad | Package-buy 1 to 3 strong level-1 terms | fixed bidding, separate roots when risk differs |
| SP Manual Exact | Only for a must-test ranking or occupation word | do not default to exact scaling before baseline data |

Use broad only after reviewing full-traffic range and negative roots.

## Bid rules

- Start near the lower edge of credible exposure when the goal is baseline discovery.
- Fixed bidding is the default for new tests because it keeps bid interpretation clean.
- Do not default to dynamic up/down until a baseline bid has been found.
- SIF PPC bid is the primary bid reference for this skill.

## Budget rules

- Daily budget usually equals estimated CPA times 3 to 5.
- If CPA is unknown, estimate CPA as `CPC / CVR`.
- If CVR is unknown, output low/base/high scenarios and state the gap.
- Too little budget makes the test inconclusive.

## Pass/fail rules

Pass signals:

- stable impressions on target words
- CTR not clearly below placement expectation
- CVR near category or product expectation
- CPA compatible with gross profit or launch investment plan
- search terms are relevant and can build keyword weight

Fail signals:

- no exposure after 2 to 3 days at a reasonable bid
- only low-quality product page exposure
- broad or auto triggers wrong roots
- high spend with no orders and no ranking/intervention value
- CPC implies impossible CPA under realistic CVR

## Exposure failure checklist

If exposure cannot run:

1. Check actual bid, not only visible base bid.
2. Check category/node and ad eligibility.
3. Check restricted terms or listing issues.
4. Check whether early poor performance reduced delivery.
5. Check whether bid is below the traffic layer being targeted.
