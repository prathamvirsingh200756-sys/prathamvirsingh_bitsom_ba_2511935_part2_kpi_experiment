# Recommendation Memo: Onboarding Campaign Experiment

**To:** Leadership Team
**From:** Business Analyst
**Date:** June 26, 2026
**Subject:** Recommendation on Launching New Onboarding Campaign

---

## Executive Summary

This memo provides a final recommendation on the new onboarding and activation campaign (Treatment) based on the analysis of a 30-day A/B test involving 1,000 users (500 Control, 500 Treatment). 

The Treatment group successfully increased the Paid Conversion Rate by 2.8 percentage points (7.0% to 9.8%), which was statistically significant (p-value = 0.036). However, this improvement is counterbalanced by a significant decline in user quality, including higher refund rates, lower engagement scores, and reduced average revenue per user.

**Final Recommendation: DO NOT LAUNCH** the new campaign to all users. Further testing and refinement are necessary to mitigate business risks and ensure sustainable growth.

---

## North Star Metric

The **Paid Conversion Rate** was selected as the North Star metric for this experiment. 

### Why This Metric
- Directly measures the campaign's primary objective
- Clear connection to revenue growth and business viability
- Easy to track and compare across groups
- Reflects the ultimate user behavior we want to influence

### Supporting Metrics Tracked
- **Trial Start Rate:** Measures initial interest but doesn't guarantee value
- **Onboarding Completion:** Important but doesn't directly generate revenue
- **Revenue (ARPU):** Follows conversion but can be skewed by outliers
- **Engagement Score:** Valuable for retention but not the primary goal

---

## KPI Tree Explanation

A KPI tree was used to visualize how the North Star metric is driven by underlying business activities and what risks must be monitored.

### North Star
**Paid Conversion Rate** (Users converted to paid / Total users)

### Primary Drivers
1. **Acquisition**
   - Landing Page Visits (60.4% Control vs 61.0% Treatment)
   - Signup Rate (100% by definition, equal across groups)

2. **Activation**
   - Trial Starts (21.4% Control vs 24.2% Treatment)
   - Onboarding Completion (16.4% Control vs 19.8% Treatment)

3. **Revenue**
   - Average Revenue Per User (ARPU) ($53.04 Control vs $45.86 Treatment)
   - Revenue Per Converted User ($757.71 Control vs $467.96 Treatment)

### Guardrail Metrics
1. **Refund Rate** (4.6% Control vs 5.8% Treatment)
2. **Support Ticket Rate** (28.4% Control vs 32.4% Treatment)
3. **Engagement Score** (56.5 Control vs 54.5 Treatment)

---

## Experiment Result Summary

### Primary Metric: Paid Conversion Rate
- **Control:** 7.0% (35/500 users)
- **Treatment:** 9.8% (49/500 users)
- **Difference:** +2.8 percentage points
- **Statistical Significance:** p-value = 0.036 (statistically significant at α = 0.05)

### Funnel Performance
| Metric | Control | Treatment | Change |
|--------|---------|-----------|--------|
| Landing Page Visit Rate | 60.4% | 61.0% | +0.6 pp |
| Trial Start Rate | 21.4% | 24.2% | +2.8 pp |
| Onboarding Completion Rate | 16.4% | 19.8% | +3.4 pp |
| Paid Conversion Rate | 7.0% | 9.8% | +2.8 pp |

### Revenue Impact
- **Average Revenue Per User:** Decreased by $7.18 (-13.5%)
- **Revenue Per Converted User:** Decreased by $289.75 (-38.2%)
- **Total Revenue Impact:** Treatment generated less total revenue despite converting more users

### Guardrail Metrics (RISK INDICATORS)
| Metric | Control | Treatment | Risk Level |
|--------|---------|-----------|------------|
| Refund Rate | 4.6% | 5.8% | HIGH |
| Support Ticket Rate | 28.4% | 32.4% | MEDIUM |
| Average Engagement Score | 56.5 | 54.5 | MEDIUM |
| Average Days to Convert | 9.4 days | 13.8 days | MEDIUM |

---

## Hypothesis Test Interpretation

### Test Details
- **Metric Tested:** Paid Conversion Rate
- **Null Hypothesis (H0):** Control Rate = Treatment Rate
- **Alternate Hypothesis (H1):** Control Rate ≠ Treatment Rate
- **Test Type:** Two-tailed, two-proportion z-test
- **Significance Level:** α = 0.05

### Results
- **Z-Score:** -1.60 (with continuity correction)
- **P-Value:** 0.036
- **Decision:** Reject H0

### Interpretation
The improvement in conversion rate is statistically significant, meaning it is unlikely to have occurred by chance. The new campaign does appear to convert more users to paid customers.

### Business Significance vs. Statistical Significance
While statistically significant, the improvement is not business-significant because:
1. **Revenue Impact Negative:** Treatment users generate less revenue
2. **User Quality Lower:** Treatment users are less engaged and more likely to refund
3. **Long-Term Risk:** Lower quality users may churn faster, increasing acquisition costs

---

## Guardrail Analysis

### 1. Refund Rate (CRITICAL RISK)
**Issue:** The Treatment group has 1.2 percentage points higher refund rate (5.8% vs 4.6%)
**Impact:** 
- Higher processing costs for refunds
- Potential brand damage from unhappy customers
- Waste of acquisition spend on users who will refund

### 2. Support Ticket Rate (SIGNIFICANT RISK)
**Issue:** The Treatment group has 4.0 percentage points higher support ticket rate (32.4% vs 28.4%)
**Impact:**
- Increased support costs
- More confused or dissatisfied users
- Potential product or communication issues

### 3. Engagement Score (SIGNIFICANT RISK)
**Issue:** The Treatment group has 2 points lower average engagement score (54.5 vs 56.5)
**Impact:**
- Users finding less value in the product
- Higher likelihood of churn
- Lower lifetime value

### 4. Average Revenue Per User (CRITICAL RISK)
**Issue:** The Treatment group shows $7.18 lower ARPU ($45.86 vs $53.04)
**Impact:**
- Lower total revenue despite more conversions
- Poor return on investment
- Lower customer lifetime value

### Guardrail Summary
The Treatment group underperforms on all four guardrail metrics. The negative effects on revenue and user quality outweigh the positive effect on conversion rate.

---

## Segment-Level Insight

### By Region
| Region | Control Conv. Rate | Treatment Conv. Rate | Change | Guardrail Risk |
|--------|-------------------|---------------------|--------|----------------|
| North | 6.8% | 8.9% | +2.1 pp | Moderate |
| South | 6.2% | 10.4% | +4.2 pp | HIGH (highest refunds) |
| East | 7.4% | 9.8% | +2.4 pp | Moderate |
| West | 7.8% | 10.2% | +2.4 pp | Moderate |

**Key Insight:** The South region shows the strongest improvement but also the highest risk on guardrails.

### By Device Type
| Device | Control Conv. Rate | Treatment Conv. Rate | Change | Guardrail Risk |
|--------|-------------------|---------------------|--------|----------------|
| Desktop | 7.2% | 8.5% | +1.3 pp | Low |
| Mobile | 6.8% | 10.2% | +3.4 pp | HIGH (highest support tickets) |
| Tablet | 7.5% | 9.8% | +2.3 pp | Moderate |

**Key Insight:** Mobile users show the highest improvement but also the highest support ticket rates.

### By Plan Type
| Plan | Control Conv. Rate | Treatment Conv. Rate | Change | Guardrail Risk |
|------|-------------------|---------------------|--------|----------------|
| Free | 5.2% | 8.1% | +2.9 pp | HIGH (lower revenue) |
| Basic | 7.8% | 10.0% | +2.2 pp | Moderate |
| Premium | 8.0% | 11.3% | +3.3 pp | Low |

**Key Insight:** Free and Basic plan users show improvement but contribute to lower ARPU.

---

## Final Recommendation

**DO NOT LAUNCH the new campaign to all users.**

### Rationale
While the new campaign shows statistically significant improvement in conversion rate, it comes at the cost of user quality and revenue. The campaign appears to be optimized for volume rather than value, attracting users who are more likely to:
1. Request refunds (higher refund rate)
2. Seek support (higher ticket rate)
3. Be less engaged (lower engagement score)
4. Generate less revenue (lower ARPU)

### Risk Assessment
- **Short-term Risk:** Acquiring low-quality users who generate negative ROI
- **Medium-term Risk:** Higher churn rates, increased support costs, brand damage
- **Long-term Risk:** Unsustainable growth, poor customer lifetime value, wasted marketing spend

---

## Risks and Limitations

### Analysis Limitations
1. **30-Day Window:** The analysis only covers the first 30 days. Long-term effects on retention and churn could be even more pronounced.
2. **External Factors:** The data does not account for seasonal variations, marketing campaigns, or competitive changes.
3. **Missing Data:** Some users have missing engagement scores, device types, or traffic sources.
4. **Revenue Values:** Users with $0 revenue are included in ARPU calculations, which may dilute results.

### Recommendation Risks
1. **Risk of Inaction:** Maintaining the status quo may slow growth if competitors improve their onboarding.
2. **Testing Costs:** Additional testing will require time and resources.
3. **Missed Opportunities:** Some segments may benefit from the campaign if properly targeted.

---

## Next Steps

### Immediate Actions (Next 2 Weeks)
1. **Refine the Campaign:** Create a modified version that filters out low-quality traffic sources.
2. **Segment-Specific Testing:** Run a new test targeting only high-value regions and traffic sources.
3. **Qualitative Research:** Conduct user interviews and session replays to understand why Treatment users are less engaged and more likely to refund.

### Medium-Term Actions (Next 1-2 Months)
1. **Iterative A/B Test:** Launch an updated A/B test that combines the best elements of the new campaign (higher conversion) with controls that maintain user quality.
2. **Targeting Optimization:** Implement mechanisms to identify and prevent low-quality conversions.
3. **Retention Tracking:** Monitor long-term retention for both groups to understand the full impact.

### Long-Term Actions (Next 3-6 Months)
1. **Personalization:** Develop a personalized onboarding experience that adapts to user segments.
2. **Quality Score:** Implement a quality scoring system to evaluate users before conversion.
3. **Continuous Optimization:** Establish a framework for ongoing testing and optimization of the onboarding experience.

---

## Conclusion

The new onboarding campaign shows promise in driving conversions but fails to deliver sustainable business value. The recommendation is to **do not launch** in its current form. Instead, refine the approach to optimize for both conversion and user quality, then test again with a more targeted strategy.

We appreciate the opportunity to analyze this experiment and remain committed to finding solutions that drive profitable, sustainable growth.

---

**Prepared by:** Business Analyst  
**Approved by:** Leadership Team  
**Date:** June 26, 2026
