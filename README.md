# Transactional-Fraud-Detection
# Objective
To create an interactive dashboard in Power BI that summarizes key findings from all previous phases, visualizes fraud patterns and transaction trends, and presents actionable insights for non-technical stakeholders.
Tasks Performed

Prepared a consolidated dashboard dataset combining cleaned transaction data, Phase 3 engineered features, fraud labels, and risk segments
Built KPI cards for Total Transactions, Total Transaction Value, Average Transaction Amount, Fraud Count, and Fraud Rate %
Created a Risk Segment bar chart showing distribution of Low Risk, Medium Risk, and High Risk (Flagged) transactions
Built a line chart showing daily transaction volume trends over the dataset's time window
Created a donut chart showing fraud distribution across Debit and Credit transaction types
Added interactive slicers for Channel, Risk Segment, and Customer Occupation to allow live filtering
Applied consistent color coding (dark red for fraud-related visuals) for clear visual storytelling
Documented key insights and recommendations based on dashboard findings

# Deliverables

Power BI Dashboard file (.pbix)
Dashboard screenshot (PNG)
Consolidated dashboard dataset (dashboard_data.csv)
Key insights and recommendations

# Key Findings

2,512 total transactions analyzed with a total value of ₹747.56K and an average transaction amount of ₹297.59
111 transactions flagged as fraud, representing a 4.42% fraud rate — realistic and consistent with real-world fraud benchmarks
75.68% of fraud cases (84 transactions) occurred via Debit transactions, with the remaining 24.32% (27 transactions) via Credit
Risk segmentation shows the majority of transactions are Low Risk, with High Risk (Flagged) forming a small, targeted subset of only 111 transactions — keeping manual review feasible
Daily transaction volume fluctuates between approximately 60–120 transactions per day, with a notable decline after day 28–30 that warrants further investigation
Interactive slicers allow drill-down by Channel, Risk Segment, and Customer Occupation to identify high-risk segments in real time

# Limitations

The fraud label used in this dashboard is synthetically generated from rule-based thresholds (Phase 3), not confirmed real-world fraud cases — findings should be interpreted as a baseline analytical model rather than validated fraud detection
All transactions occur within a narrow time window (4–6 PM daily), limiting time-based fraud pattern analysis
A production dashboard would require a genuine fraud label sourced from confirmed chargebacks or fraud investigation records to provide fully reliable business insights

# Recommendation
Since High Risk transactions form a small, well-isolated group of 111 cases, the immediate priority should be building a manual review workflow targeting that segment. In parallel, the synthetic fraud rules should be validated against any real fraud reports or chargebacks if they become available, to confirm whether the amount and login-attempt thresholds genuinely predict fraud behavior in practice.
