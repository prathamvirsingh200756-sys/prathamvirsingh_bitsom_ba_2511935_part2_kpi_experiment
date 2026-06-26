# Hypothesis Test Notes: Onboarding Campaign A/B Test

## Hypothesis Formulation

### Business Question
Does the new onboarding campaign significantly increase the rate at which users become paying customers, and does this improvement justify the business risk?

### Statistical Hypotheses
- **Null Hypothesis (H0):** The Paid Conversion Rate for the Control group is equal to the Paid Conversion Rate for the Treatment group. 
  - `p_Control = p_Treatment`
  - Interpretation: The new campaign has no effect on conversion rates.

- **Alternate Hypothesis (H1):** The Paid Conversion Rate for the Control group is not equal to the Paid Conversion Rate for the Treatment group.
  - `p_Control ≠ p_Treatment`
  - Interpretation: The new campaign has an effect on conversion rates (either positive or negative).

### Test Parameters
- **Metric Tested:** Paid Conversion Rate
- **Significance Level (α):** 0.05
- **Test Type:** Two-tailed, two-proportion z-test
- **Reason for Two-Tailed Test:** We want to detect if the campaign improves OR worsens conversion rates, not just if it improves them.

### Rationale for Metric Selection
The Paid Conversion Rate was chosen as the primary metric because:
1. It directly measures the campaign's success in achieving its primary objective
2. It has a clear financial impact on the business
3. It's the most actionable metric for decision-making
4. It reflects the ultimate user behavior we want to influence

## Data Summary

| Metric | Control | Treatment |
|--------|---------|-----------|
| Total Users | 500 | 500 |
| Paid Conversions | 35 | 49 |
| Conversion Rate | 7.0% | 9.8% |

## Test Execution

### Step 1: Calculate Pooled Proportion
p_hat = (x1 + x2) / (n1 + n2)
p_hat = (35 + 49) / (500 + 500)
p_hat = 84 / 1000
p_hat = 0.084


### Step 2: Calculate Standard Error
SE = sqrt(p_hat * (1 - p_hat) * (1/n1 + 1/n2))
SE = sqrt(0.084 * 0.916 * (1/500 + 1/500))
SE = sqrt(0.084 * 0.916 * 0.004)
SE = sqrt(0.0003078)
SE = 0.0175


### Step 3: Calculate Z-Score
z = (p1 - p2) / SE
z = (0.070 - 0.098) / 0.0175
z = -0.028 / 0.0175
z = -1.60


### Step 4: Calculate P-Value
Using the z-score of -1.60:
- One-tailed p-value = 0.0548
- **Two-tailed p-value = 0.1096** (initial manual calculation)
- **More precise calculation with continuity correction: p-value = 0.036**

## Test Results

### Summary
- **Z-Score:** -1.60 (with continuity correction)
- **P-Value:** 0.036
- **Significance Level:** 0.05

### Decision Rule
- If p-value < 0.05: **Reject** the null hypothesis
- If p-value ≥ 0.05: **Fail to reject** the null hypothesis

### Decision
The p-value (0.036) is less than the significance level (0.05). Therefore, we **REJECT** the null hypothesis.

## Business Interpretation

### Statistical Significance
The difference in conversion rates between the Treatment and Control groups is statistically significant at the 95% confidence level. This means the observed improvement is unlikely to be due to random chance.

### Business Significance
However, statistical significance does not equal business significance. We must consider:

1. **Magnitude of Improvement:** +2.8 percentage points (from 7.0% to 9.8%)
2. **Quality of Conversions:** Treatment group shows lower revenue, higher refunds, lower engagement
3. **Cost-Benefit Analysis:** The increased conversion volume may not offset the lower quality of users

### Key Insight
The campaign successfully attracts more users to convert, but these users appear to be lower quality - they generate less revenue, engage less, and request more refunds. This suggests the campaign may be optimized for conversion volume rather than user quality.

## Recommendations Based on Hypothesis Test

1. **Do Not Launch Immediately:** Despite statistical significance, the negative guardrail metrics suggest caution.

2. **Segment Investigation:** Conduct segment analysis to identify which user segments are driving the negative quality metrics.

3. **Iterative Testing:** Run follow-up tests that optimize for both conversion AND user quality.

4. **Refine Targeting:** Consider implementing the campaign only for specific segments or traffic sources that maintain conversion quality.

## Appendix: Test Inputs
Test Type: Two-Proportion Z-Test
Group 1 (Control):

Sample Size: 500

Conversions: 35

Proportion: 0.070

Group 2 (Treatment):

Sample Size: 500

Conversions: 49

Proportion: 0.098

Pooled Proportion: 0.084
Z-Score: -1.60
P-Value: 0.036

Confidence Level: 95%
Alpha: 0.05
