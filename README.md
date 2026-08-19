# EXCEL-HEALTHCARE-ANALYSIS-AND-INSIGHT-
# 🏥 Healthcare Analysis & Insight Dashboard

An interactive Excel dashboard (`Dashboard` sheet) analyzing 2,335 health-insurance customers across smoking, weight, diabetes, hospitalisation tier, and demographic factors. Below is a breakdown of every chart on the dashboard and the insight it surfaces, plus how to use the dashboard's slicers.

## 📋 Dashboard Contents

The dashboard is built from pivot tables and includes **live slicers** for **Smoker Status**, **Weight Status**, and **Hospital Tier**, so any chart below can be filtered interactively.

### 1. Cancer History by Smoker Status *(pie chart)*
| Smoker | No Cancer History | Cancer History | Total |
|---|---|---|---|
| No | 1,728 | 119 | 1,847 |
| Yes | 463 | 25 | 488 |

**Insight:** Cancer history is proportionally similar across smokers and non-smokers (~5–6% in both groups) — in this dataset, smoking doesn't show an elevated link to reported cancer history, which is worth flagging for a closer look since it runs against clinical expectation.

### 2. Number of Major Surgeries by Transplant Status *(pie chart)*
| Any Transplant | Sum of Major Surgeries | Avg. HbA1C |
|---|---|---|
| No | 1,417 | 6.67 |
| Yes | 162 | 5.19 |

**Insight:** Customers with a transplant history account for a small share (~10%) of total major surgeries logged, and actually show a *lower* average HbA1C (blood sugar level) than the non-transplant group.

### 3. Average Charge by Weight Status × Diabetes Status *(bar chart)*
| Weight Status | Diabetes | Normal | Prediabetes |
|---|---|---|---|
| Normal Weight | $12,510 | $7,897 | $10,390 |
| **Obesity** | **$19,083** | $15,127 | $15,465 |
| Overweight | $13,910 | $10,390 | $10,042 |
| Under Weight | $7,425 | $6,911 | $5,626 |

**Insight:** Obese + diabetic customers are the most expensive segment on the dashboard ($19,083 avg.) — roughly **2.4x** the cheapest segment (underweight + prediabetic, $5,626). Weight status and diabetes status compound each other rather than acting independently.

### 4. Average Charge by State × Hospital Tier *(bar chart)*
| State | Tier 1 | Tier 2 | Tier 3 |
|---|---|---|---|
| R1016 | $39,869 | $16,076 | $8,133 |
| R1017 | $34,071 | $11,366 | $8,667 |
| R1018 | $33,476 | $10,140 | $12,571 |
| R1011 | $33,081 | $18,997 | $9,250 |
| R1013 | $30,878 | $8,460 | $6,891 |
| **Grand Total** | **$30,033** | **$11,874** | **$9,462** |

**Insight:** Tier-1 hospitals cost roughly **2.5–3x** more than Tier-2 and **3–4x** more than Tier-3 in nearly every state, with R1016 showing the widest gap ($39,869 vs. $8,133). This pattern holds consistently across states, suggesting it's a structural tier effect rather than a regional one.

### 5. Age vs. BMI *(scatter / correlation chart)*
**Correlation coefficient: 0.05** — essentially no relationship. BMI is spread fairly evenly across all age groups, so age is not a useful predictor of BMI in this population.

### 6. Age vs. HbA1C *(scatter / correlation chart)*
**Correlation coefficient: 0.46** — moderate positive relationship. Blood sugar (HbA1C) tends to rise with age, consistent with increasing diabetes/prediabetes risk in older customers.

### 7. Age vs. Charge *(line chart)*
**Correlation coefficient: 0.30** — mild-to-moderate positive relationship. Charges trend upward with age, but age alone explains only part of the variation — other factors (weight, diabetes, hospital tier) matter more.

## 🔎 Summary of Dashboard Insights

1. **Obesity + diabetes is the costliest combination** tracked on the dashboard ($19,083 avg. charge).
2. **Hospital tier is the single largest cost multiplier visible on the dashboard** — Tier 1 costs 2.5–4x more than Tier 2/3, consistently across nearly every state.
3. **Age correlates more strongly with HbA1C (0.46) than with charges (0.30) or BMI (0.05)** — meaning age drives blood-sugar risk more directly than it drives cost or weight.
4. **Cancer history and transplant status don't show the elevated risk pattern one might expect** from smoking or major-surgery counts — both are flagged as areas to validate against source data rather than firm conclusions.

## 🖱️ Using the Dashboard

Open the `Dashboard` sheet in Excel and use the **Smoker**, **Weight Status**, and **Hospital Tier** slicers to filter all charts simultaneously — useful for drilling into a specific segment (e.g., "obese smokers in Tier-1 hospitals").

## 📁 Repo Structure

```
├── MODULE_1_HEALTHCARE_ANALYSIS_AND_INSIGHT.xlsx   # Data, pivot tables, and interactive dashboard
└── README.md                                        # This file
```

---
*Based on the `Dashboard` sheet's pivot charts (Pivot Table sheet as source), covering 2,335 health-insurance customers.*
