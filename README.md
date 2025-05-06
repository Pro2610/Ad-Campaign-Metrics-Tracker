# 📈 UTM Campaign Analysis: Facebook & Google Ads Performance Metrics

## 🔍 Overview
This project analyzes paid traffic performance across Facebook and Google Ads using UTM campaign tags.  
By combining daily advertising data, the analysis calculates essential marketing KPIs such as CTR, CPC, CPM, and ROMI — providing actionable insights into campaign effectiveness.

## 🧰 Tools & Technologies
- SQL (BigQuery or PostgreSQL)
- COALESCE, CASE, REGEX (for UTM extraction)
- Marketing metrics: CTR, CPC, CPM, ROMI
- Data from: `facebook_ads_basic_daily`, `google_ads_basic_daily`

## 🎯 Business Goal
To assess and compare marketing campaign performance by UTM tag across different platforms, helping marketers optimize spend and returns.

## 📈 Key Metrics Calculated
| Metric | Description |
|--------|-------------|
| **CTR** | Click-Through Rate = Clicks / Impressions × 100 |
| **CPC** | Cost Per Click = Spend / Clicks |
| **CPM** | Cost Per Mille = Spend per 1,000 Impressions |
| **ROMI** | Return on Marketing Investment = Revenue / Spend |

## 🧪 Sample Logic Snippet
```sql
-- ROMI calculation
CASE
  WHEN SUM(spend) = 0 THEN 0
  ELSE SUM(value) * 1.0 / SUM(spend)
END AS ROMI
