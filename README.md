# Meridian Trust Bank — AI Governance Portfolio

A hands-on GRC portfolio applying AI governance frameworks primarily the **NIST AI Risk Management Framework**, alongside **SR 11-7 / OCC model risk guidance**, **ECOA/Reg B**, **BSA/AML**, and related financial services regulation to a fictional regional bank with a realistic AI system inventory.

This repo exists to demonstrate applied, practical understanding of AI risk and governance, not just familiarity with framework text. The risk assessments, the gap analyses, the dashboard was built by working through real-looking scenarios end to end.

## Why a fictional bank

Meridian Trust Bank doesn't exist. It's a $38B regional bank with a defined org structure, a six-system AI/ML inventory, and known governance gaps, built specifically to give each exercise a consistent, realistic environment to work against. Using a fictional institution means the risk scenarios can be designed deliberately (a chatbot launched without MRM review, a vendor fraud model never independently validated) without implicating or misrepresenting any real company's actual practices. See [`company-profile.md`](./company-profile.md) for the full org structure, systems inventory, and regulatory surface.

## What's inside

| System | Function applied | Finding | Link |
|---|---|---|---|
| CreditScore-ML | Map | Adverse action reason codes don't cleanly map to model feature importance | [risk map](./02-map/creditscore-ml-risk-map.md) |
| Watchtower (AML) | Measure | No drift monitoring; alert precision degraded 18% since last tuning | [metrics](./03-measure/watchtower-alert-metrics.md) |
| SentryAI (fraud) | Manage | Vendor model never independently validated; contract renewal risk window | [response plan](./04-manage/sentryai-vendor-risk-response.md) |
| Org-wide | Govern | No AI governance committee; shadow AI deployment (chatbot) bypassed MRM | [gap analysis](./01-govern/govern-gap-analysis.md) |


## Interactive dashboard

A React/Chart.js risk monitoring dashboard modeling Meridian's AI systems, risk scoring, and regulatory mapping. [Live demo](#) · [source](./dashboard)


## Structure

```
01-govern/      org-level governance gap analysis, committee charter draft
02-map/         per-system risk identification and context mapping
03-measure/     metrics, testing approaches, and assessment write-ups
04-manage/      prioritization, response plans, mock committee briefings
dashboard/      React + Chart.js risk monitoring tool
company-profile.md   Meridian Trust Bank reference (org, systems, regulatory surface)
```

## License

MIT — see [LICENSE](./LICENSE). Meridian Trust Bank is a fictional entity created for this project and is not associated with any real financial institution.
