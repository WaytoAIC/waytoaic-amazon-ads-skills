---
name: waytoaic-ads-ad-report-diagnosis
description: Diagnose Amazon Ads reports using Soju course rules. Use when the user provides Search Term, Targeting, Placement, Advertised Product, Purchased Product, SP/SB/SD reports, or asks for 报表诊断, 重复投放, 漏斗断层, 推广盲区, 无效花费, 正向干预, CTR/CVR/CPC/CPA/ACOS/ROAS analysis, or ad_diagnosis.md/action_plan.csv.
---

# WaytoAIC-Ads Ad Report Diagnosis

This skill diagnoses Amazon Ads report exports using Soju's report-analysis rules. It can reuse `amazon-targeting-structure-report` logic when the input is Sponsored Products Advertised Product plus Targeting report.

## Read first

- `../shared/waytoaic-ads-operating-boundaries.md`
- `references/ad-report-rules.md`
- `templates/ad-diagnosis-output.md`
- Existing skill when relevant: `/Users/wesleyzane/.codex/skills/amazon-targeting-structure-report/SKILL.md`

## Accepted inputs

- Search Term report
- Targeting report
- Placement report
- Advertised Product report
- Purchased Product report
- SP, SB, or SD report exports
- Keyword map from `waytoaic-ads-keyword-map`
- target ACOS, gross profit, average clicks per order, or target CPA

## Workflow

1. Identify report types and date range.
2. Calculate CTR, CVR, CPC, CPA, ACOS, ROAS, spend share, sales share, order share, and zero-order spend.
3. Diagnose:
   - repeated targeting
   - bid structure disorder
   - main keyword funnel break
   - keyword-map blind spots
   - high spend without natural/ranking evidence
   - positive, invalid, or negative intervention
4. If the input matches the existing targeting-structure skill, run or mirror that script instead of reimplementing the same logic.
5. Produce `ad_diagnosis.md` style output and an action table.

## Output rules

- Separate facts, Soju rules, AI judgment, and recommended actions.
- Mark bid down, budget down, negative, pause, or campaign merge as `approval_required=true`.
- Do not claim ranking impact unless ranking or SIF keyword evidence is present.
