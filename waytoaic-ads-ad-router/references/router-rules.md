# Router Rules

## Intent detection

Route by the user's actual object and decision point, not by course day.

| Signal in request | Primary route | Optional companion |
| --- | --- | --- |
| keywords, roots, competitor ASIN terms, negatives | `waytoaic-ads-keyword-map` | `waytoaic-ads-profit-tacos-planner` if budget/profit is mentioned |
| new product, baseline bid, can it run exposure | `waytoaic-ads-launch-test-planner` | `waytoaic-ads-keyword-map` |
| reports, Search Term, Targeting, Placement, ACOS problem | `waytoaic-ads-ad-report-diagnosis` | `waytoaic-ads-bid-placement-control` |
| TOS, ROS, PP, placement multiplier | `waytoaic-ads-bid-placement-control` | `waytoaic-ads-profit-tacos-planner` |
| scale, expand, shrink, merge, pause | `waytoaic-ads-scale-shrink-planner` | `waytoaic-ads-ad-report-diagnosis` |
| parent, child ASIN, main SKU, variation test | `waytoaic-ads-variant-strategy` | `waytoaic-ads-keyword-map` |
| CPA, TACOS, profit, order split | `waytoaic-ads-profit-tacos-planner` | `waytoaic-ads-scale-shrink-planner` |
| seasonal, holiday, peak, trend | `waytoaic-ads-seasonality-planner` | `waytoaic-ads-launch-test-planner` |

## Stage labels

- `pre-launch`: product or keywords are not ready for ads.
- `test`: baseline exposure, CPC, CTR, CVR, and CPA are being established.
- `scale`: positive traffic exists and needs more volume.
- `stable`: ranking, profit, or TACOS needs maintenance.
- `shrink`: spend must be reduced or structure simplified.
- `seasonal`: timing is driven by trend stage.

## Partial-data behavior

- If the user gives ASINs but no reports, use MCP-backed skills and state report limitations.
- If the user gives reports but no ASIN, report diagnosis can still run.
- If profit data is missing, do not decide profitable vs investment ads; create scenarios.
- If seasonality dates are missing, use trend-check workflow instead of exact A-B-C-D-E claims.

## Combined output

When multiple skills are relevant, choose at most three:

1. one primary diagnosis skill
2. one planning skill
3. one profit or timing skill if needed

Do not bury the user in all modules.
