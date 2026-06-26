# KPI Experiment Analysis: Onboarding Campaign A/B Test

## Business Context
Our company, a subscription-based digital product provider, has developed a new onboarding and activation campaign. The goal is to improve user conversion and early engagement. We conducted an A/B test by splitting users into two groups:
- **Control:** Existing onboarding experience.
- **Treatment:** New campaign experience.

The leadership team needs a data-driven recommendation on whether to launch this new campaign to all users.

## Dataset Description
The dataset, `campaign_experiment_data.xlsx`, contains 1,018 user records. Key features include:
- **User & Segmentation:** `user_id`, `signup_date`, `experiment_group`, `region`, `device_type`, `traffic_source`, `plan_type`.
- **Funnel Metrics:** `visited_landing_page`, `started_trial`, `completed_onboarding`, `converted_to_paid`.
- **Business Outcomes:** `revenue_30d`, `refund_requested`, `support_tickets_30d`, `engagement_score`.

## North Star Metric
The selected North Star metric for this experiment is **Paid Conversion Rate**.

## KPI Tree Summary
The KPI tree breaks down the Paid Conversion Rate into:
1.  **Acquisition:** Visits, Signups.
2.  **Activation:** Trial Starts, Onboarding Completion.
3.  **Revenue:** ARPU, Revenue per Conversion.

**Guardrail metrics** (Refund Rate, Support Ticket Rate, Engagement Score) are monitored to ensure business health.

## Experiment Analysis Approach
1.  **Data Cleaning:** Missing values and outliers in revenue were checked. 6 users in the Control group had revenue of `0`, and 5 users in the Treatment group had revenue of `0`. A small number of records had missing `device_type` or `traffic_source` values, which were noted but not imputed to avoid bias.
2.  **Exploratory Analysis:** Group counts and segment distributions were analyzed for balance.
3.  **Summary Metrics:** Calculated key performance indicators for Control vs. Treatment groups.
4.  **Segment Analysis:** Metrics were broken down by Region, Device Type, and Plan Type.
5.  **Hypothesis Testing:** A two-tailed t-test was performed to compare the Paid Conversion Rate between the Control and Treatment groups.

## Hypothesis Test Summary
- **Null Hypothesis (H0):** The Paid Conversion Rate is the same for Control and Treatment groups (Control_Conversion = Treatment_Conversion).
- **Alternate Hypothesis (H1):** The Paid Conversion Rate is different for Control and Treatment groups (Control_Conversion != Treatment_Conversion).
- **Metric Tested:** Paid Conversion Rate.
- **Significance Level (α):** 0.05.
- **Test Type:** Two-tailed, two-proportion z-test.
- **Result:** The p-value is approximately **0.036**, which is less than 0.05. We reject the null hypothesis. The improvement in conversion rate is statistically significant.

## Guardrail Metrics Considered
To ensure we don't make a decision based solely on conversion, we evaluated these guardrail metrics:
- **Refund Rate**
- **Support Ticket Rate**
- **Engagement Score**
- **Average Revenue Per User (ARPU)**

The Treatment group showed significantly worse performance on refund rate, engagement score, and ARPU.

## Final Recommendation
**DO NOT LAUNCH THE NEW CAMPAIGN TO ALL USERS.** While the campaign shows a statistically significant increase in conversion, it generates lower-quality, less profitable users who are more likely to churn or request refunds. This poses a long-term business risk.

**Next Steps:**
- Run a new, segmented A/B test that combines the high-engagement aspects of the new campaign with the high-quality user acquisition strategies of the control group.
- Implement mechanisms to identify and prevent low-quality conversions (e.g., limiting the campaign to users from high-value traffic sources).
- Conduct a qualitative analysis (e.g., user interviews, session replays) to understand the poor user experience and high refund rates.

## Assumptions and Limitations
- The analysis assumes users were randomly assigned to the Control and Treatment groups.
- Revenue values of `0` and missing values are inherent to the data and were handled by exclusion from relevant calculations (e.g., ARPU) where appropriate, but their presence does not undermine the comparative analysis.
- The results are based on a 30-day window; long-term retention effects are unknown.

## Screenshots Included
1.  `screenshots/summary_metrics.png` - Control vs Treatment summary table.
2.  `screenshots/hypothesis_test_output.png` - Hypothesis test output.
3.  `screenshots/kpi_tree_preview.png` - KPI tree preview.
