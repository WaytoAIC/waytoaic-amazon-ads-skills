# Profit TACOS Rules

## Formulas

- `CPA = spend / ad orders`
- `CPA = CPC / CVR`
- `ACOS = spend / ad sales`
- `ACOS = CPA / price`
- `ROAS = ad sales / spend`
- `TACOS = ad spend / total sales`
- `TACOS = ACOS x ad order share` when price is stable
- `ad order share = ad orders / total orders`

## Profit classification

Profitable ad:

- `CPA < gross profit`
- goal is to increase profitable ad orders and widen `gross profit - CPA`

Investment ad:

- `CPA >= gross profit`
- goal is natural orders, ranking, occupation, or future profit
- must have a cap and a reason

Waste:

- CPA is high and no ranking, natural, defense, or learning value exists

## Budget logic

Investment campaign budget:

- `daily budget = CPA x expected ad orders`
- cap the downside
- stop or shrink if it cannot create payback

Profitable campaign budget:

- no artificial cap is needed in theory
- still check inventory, campaign control, and diminishing returns

## TACOS interpretation

TACOS falls when:

- CPA falls
- price rises without hurting CVR
- natural order share rises
- ad order share falls without losing total profitable volume

During launch:

- TACOS can exceed profit rate if the investment is intentional and capped.

During stable period:

- TACOS should move inside the profit boundary.

## Reverse planning

Inputs:

- target total orders or total sales
- target TACOS
- price
- CPC
- CVR

Steps:

1. Calculate CPA from CPC/CVR.
2. Calculate allowed ad spend from target TACOS.
3. Calculate allowed ad orders from allowed spend/CPA.
4. Calculate required natural orders as total orders minus allowed ad orders.
5. Compare with current natural/ad split.

## Shrink triggers

Shrink investment traffic when:

- no investment value remains
- positive intervention is not happening
- enough volume cannot be reached
- target position is reached
- ranking or natural contribution hits a bottleneck

Do not shrink profitable ads just because ACOS is above a generic target if actual CPA is below gross profit and total profit increases.
