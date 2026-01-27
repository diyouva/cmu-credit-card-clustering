# Transactional Data EDA - Detailed Analysis
**Author:** Rizaldy
**Business Objective:** Increase Utilization Rate to drive sales volume and revenue

---

## Transactional Features Overview

| Feature | Description |
|---------|-------------|
| Credit_Limit | Maximum credit available to customer |
| Total_Revolving_Bal | Balance carried over from month to month |
| Avg_Open_To_Buy | Available credit (Credit_Limit - Total_Revolving_Bal) |
| Total_Amt_Chng_Q4_Q1 | Change in transaction amount (Q4 vs Q1) |
| Total_Trans_Amt | Total transaction amount in last 12 months |
| Total_Trans_Ct | Total transaction count in last 12 months |
| Total_Ct_Chng_Q4_Q1 | Change in transaction count (Q4 vs Q1) |
| Avg_Utilization_Ratio | Credit utilization (Total_Revolving_Bal / Credit_Limit) |

---

## 1. Descriptive Statistics

**Justification:** Understanding the central tendency, spread, and distribution of transactional features helps identify potential outliers and data quality issues before clustering. This is essential for the business goal of identifying under-utilized customer segments.

**Key Metrics Explanation:**
- **CV (Coefficient of Variation):** Higher CV indicates more variability relative to mean
- **Skewness:** >0 right-skewed, <0 left-skewed; |skew| > 1 indicates significant skew
- **IQR:** Interquartile range shows spread of middle 50% of data

---

## 2. Distribution Analysis

**Justification:** Visualizing distributions helps understand customer spending patterns and identify segments. Skewed distributions indicate presence of different customer groups (e.g., high spenders vs low spenders) - key for clustering strategy.

**Interpretation:**

1. **Credit_Limit & Avg_Open_To_Buy:** Right-skewed, most customers have lower limits
   - Indicates majority are standard card holders, few premium customers

2. **Total_Revolving_Bal:** Bimodal distribution (peaks at 0 and ~1500)
   - Two distinct groups: those who pay full balance vs those who carry debt

3. **Avg_Utilization_Ratio:** Right-skewed with many at 0
   - Many customers under-utilize their credit (TARGET FOR BUSINESS OBJECTIVE)

4. **Total_Trans_Amt & Total_Trans_Ct:** Show variation in transaction behavior
   - Good features for differentiating customer engagement levels

---

## 3. Outlier Analysis

**Justification:** Boxplots reveal outliers and data spread. For clustering, understanding outliers is crucial as they can skew cluster centroids. This helps decide if data transformation or outlier treatment is needed.

**Recommendation:** Features with high outlier % may need transformation (log, sqrt) before clustering to prevent outliers from dominating cluster formation.

---

## 4. Utilization Ratio Deep Dive (KEY BUSINESS METRIC)

**Justification:** Avg_Utilization_Ratio is the PRIMARY BUSINESS METRIC. Understanding its distribution and segments is critical for targeting under-utilized customers to increase revenue.

**Segment Definitions:**
| Segment | Threshold | Business Action |
|---------|-----------|-----------------|
| Low Utilization | ≤30% | TARGET - Increase engagement |
| Medium Utilization | 30-70% | NURTURE - Maintain/grow |
| High Utilization | >70% | MONITOR - Risk of overleveraging |

**Key Insight:**
- Majority of customers have LOW utilization (≤30%)
- These are the PRIMARY TARGETS for marketing campaigns
- Strategy: Offer rewards, cashback, or promotional rates to increase usage
- Clustering will help identify WHICH low-utilization segments to target first

---

## 5. Correlation Analysis

**Justification:** Understanding correlations helps identify redundant features and potential multicollinearity issues. For clustering, we want features that capture different aspects of customer behavior, not duplicate information.

**High Positive Correlations (potential redundancy):**

1. **Credit_Limit ↔ Avg_Open_To_Buy:** Very high correlation (~0.99)
   - RECOMMENDATION: Use only ONE of these features (prefer Credit_Limit as base metric)

2. **Total_Trans_Amt ↔ Total_Trans_Ct:** High correlation
   - Both capture transaction activity; consider keeping both as they measure different aspects (amount vs frequency)

---

## 6. Transaction Behavior Analysis

**Justification:** Transaction amount and count together reveal spending patterns. This helps identify different customer types: high frequency low value vs low frequency high value customers - critical for targeted marketing.

**Quadrant Interpretation:**

| Quadrant | Description | Strategy |
|----------|-------------|----------|
| High Amt / High Ct | Power users - high value, frequent transactions | Best customers, offer loyalty rewards to retain |
| High Amt / Low Ct | Big spenders - high value, infrequent | Opportunity to increase transaction frequency |
| Low Amt / High Ct | Frequent users - low value, many transactions | Opportunity to increase transaction value (upsell) |
| Low Amt / Low Ct | Low engagement - under-utilized segment | PRIMARY TARGET for increasing utilization rate |

---

## 7. Feature Selection Summary

**Selection Criteria:**
1. Relevant to business objective (increasing utilization)
2. Good variability (can differentiate customer segments)
3. Not highly correlated with each other (avoid redundancy)
4. Can be meaningfully interpreted for business actions

### Recommended Features for Clustering

**PRIMARY FEATURES (5 features):**
1. `Credit_Limit` - Capacity metric
2. `Total_Revolving_Bal` - Debt behavior
3. `Total_Trans_Amt` - Transaction volume
4. `Total_Trans_Ct` - Transaction frequency
5. `Avg_Utilization_Ratio` - KEY BUSINESS METRIC

**OPTIONAL FEATURES:**
- `Total_Amt_Chng_Q4_Q1` - if trend analysis is needed
- `Total_Ct_Chng_Q4_Q1` - if activity trend is important

**EXCLUDED:**
- `Avg_Open_To_Buy` - Highly correlated with Credit_Limit (redundant)
- `CLIENTNUM` - Just an identifier

---

## Preprocessing Recommendations

1. **STANDARDIZATION:** Use StandardScaler for all features (different scales)
2. **OUTLIER HANDLING:** Consider log transformation for:
   - Credit_Limit (right-skewed)
   - Total_Trans_Amt (right-skewed)
3. **NO ENCODING NEEDED:** All selected features are numerical

---

## Next Steps for Clustering

1. Combine transactional features with Life Stage features (Diyouva's EDA)
2. Apply StandardScaler to normalize all features
3. Use multiple clustering algorithms (K-Means, Hierarchical, DBSCAN)
4. Evaluate clusters using Silhouette Score and business interpretability
5. Profile clusters to identify under-utilized segments
6. Design targeted marketing strategies for each cluster
