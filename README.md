# IVT-Traffic-Analysis
IVT Anomaly Detection
Data Preparation:

Performed data cleaning and transformation in Power Query Editor:

Removed duplicates and unnecessary rows.

Added new calculated columns such as:

DateOnly – extracted clean date from datetime column.

IDFA to IP Ratio and IDFA to UA Ratio for bot activity detection.

Ensured consistent data types for accurate aggregations.

Appended multiple datasets into a single table named “Invalid 1.”

🧮 Key DAX Measures:

Requests per IDFA = SUM(Requests) / DISTINCTCOUNT(IDFA)

First IVT Date = MIN(DateOnly) when IVT_Flag = “Yes”

Avg Requests Before IVT and After IVT – calculated using filters before and after first IVT detection.

Percent Change in Requests = (After - Before) / Before

Dashboard Pages:
1.Traffic Overview

Overview of all app traffic to identify which apps are contributing to high IVT.

KPIs: Total Requests, Unique IDFAs, Average Requests per IDFA, IVT Rate (%).

Visuals:

Bar chart: Requests by App_Name

Pie chart: IVT vs Valid Traffic

Trend line: Requests per Day

Slicers: App, Date

Key Insight:
Certain apps showed abnormal spikes in requests, indicating potential automated or fraudulent activity.
IVT contribution varied by app, with a few apps driving the majority of invalid traffic.

2.App Deep Dive
Focused analysis on individual apps using a slicer.
Line chart displays traffic trends (Requests per IDFA) over time.
Vertical line marks First IVT Date, visually separating “Before” and “After” periods.
KPI cards show Avg Requests Before IVT, Avg Requests After IVT, and Percent Change.
Table shows detailed metrics — Date, Requests per IDFA, IDFA to IP Ratio, and IDFA to UA Ratio.

3.Hourly Pattern

Key Insights:
For most apps, average requests per IDFA dropped after IVT detection, suggesting that fraudulent or automated sources were filtered out effectively.
The Percent Change metric quantifies traffic reduction, confirming the impact of IVT identification.
Apps with minimal change after IVT detection may require further investigation, as fraud filtering may not be fully effective.
Ratios such as IDFA to IP and IDFA to UA helped identify anomalous behavior (e.g., many IDFAs mapped to one IP → bot activity).

#Conclusion:
The analysis successfully highlights the difference in traffic quality before and after IVT detection.
It provides a data-driven understanding of app performance and helps detect potential fraudulent activity.
Power BI’s DAX and visualization tools were used to create an interactive, dynamic, and insight-rich dashboard that supports decision-making for ad fraud prevention and traffic optimization.
