# Bid Placement Rules

## Formula

Use the course formula:

`actual bid = base bid x bidding strategy effect x placement multiplier`

Approximate strategy effects:

- Fixed bid: Amazon does not adjust the base bid.
- Down only: Amazon can lower when conversion likelihood is weak.
- Up and down: Amazon can raise for conversion likelihood; top of search can rise more than other placements.

## Placement meanings

| Placement | Role |
| --- | --- |
| TOS | few positions, highest price, ranking/occupation value, risky CPA |
| ROS | middle price, broad search-result coverage |
| PP | product page traffic, usually cheaper, many placements, can be useful for low-cost orders or occupation |

## Exposure ratio reference

When using fixed or down-only bidding and no TOS boost:

- PP impressions are often about 5 to 15 times `(TOS + ROS)`.
- PP far above that often means base bid is too low for search-result layers.
- PP below normal can mean bid is high enough to enter stronger search placements or PP delivery is restricted.

This is a diagnostic heuristic, not a law.

## Four bid levels

| Level | Meaning | Typical signal |
| --- | --- | --- |
| `a` | PP layer bid | PP huge, ROS tiny, no TOS |
| `b` | normal ROS bid | ROS appears, PP ratio normal, TOS minimal |
| `c` | high ROS / unstable TOS | TOS appears sometimes, ROS still shares |
| `d` | stable TOS | TOS has major share, ROS still meaningful, PP normal or low |

## Strategy selection

- New or test campaigns: fixed bidding.
- Stable efficiency campaigns: down-only can help conserve spend.
- Mature campaigns with known conversion: up/down can be used carefully.

## Common plays

### TOS only or TOS-heavy

Use only when:

- TOS CPA is acceptable, or
- ranking/occupation value justifies investment.

### ROS + PP

Use when:

- TOS is expensive or unstable.
- ROS and PP create acceptable CPA.

### PP-heavy

Use when:

- PP CVR is good.
- PP CPA is low.
- product-page occupation has strategic value.

### ROS-only attempt

Use lower base bid with placement multiplier only when the math can push search result placements while limiting other layers. Flag as experimental.

## Distortion warnings

Placement interpretation is unreliable when:

- auto campaign has multiple targeting groups
- broad campaign mixes very different roots
- a campaign has many unrelated targets
- old low-weight listing delivery is restricted
- budget cuts off delivery early every day
