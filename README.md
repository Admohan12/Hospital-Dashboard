🏥 Hospital Performance Analysis Dashboard
1. Project Overview
This repository contains the Power BI file (Hospital Dashboard.pbix) for a comprehensive analytical dashboard designed to monitor and visualize key performance indicators (KPIs) across a healthcare system or single hospital facility.

The dashboard provides a consolidated view of operational efficiency, patient care quality, and financial health, enabling administrators and department heads to make data-driven decisions.

Focus Area	Key Metrics	Goal
Operational Efficiency	Bed Occupancy, Average Length of Stay (ALOS), Patient Flow.	Optimize resource allocation and reduce bottlenecks.
Quality of Care	Readmission Rates, Mortality Rates, Infection Rates.	Benchmark performance against quality standards.
Financial Health	Revenue by Department, Patient Volume, Cost per Case.	Monitor and improve profitability.

Export to Sheets
2. Data Model & Structure
The dashboard is built on a Star Schema to ensure data integrity and fast filter performance. The key is linking all transactional data to central dimension tables for filtering.

Core Tables (Conceptual):
Table Name	Role	Key Column	Description
Dim_Date	Central Dimension	Date	Used for all time-based analysis and filtering.
Dim_Patient	Dimension	Patient_ID	Demographics, Admission Type, Insurance info.
Dim_Department	Dimension	Dept_ID	Details of all hospital departments (ER, Surgery, etc.).
Fact_Admissions	Fact	Admission_ID	Records of patient stays, including LOS and Discharges.
Fact_Financials	Fact	Transaction_ID	Revenue, Costs, and Billing data.

Export to Sheets
Relationships:
Dim_Date (1) ➡️ All Fact Tables (*): Filters admissions, discharges, and financial data by date.

Dim_Department (1) ➡️ Both Fact Tables (*): Filters metrics by hospital department.

Dim_Patient (1) ➡️ Fact_Admissions (*): Enables analysis by patient cohort.

3. Key Dashboard Pages & Analysis
The report is typically organized into sections focusing on critical hospital functions:

A. Executive Summary (Homepage)
KPIs: Displays high-level metrics like Total Admissions, Total Revenue, Average Length of Stay (ALOS), and Readmission Rate.

Visuals: Trends showing admissions/discharges over time and revenue breakdown by major service line.

Interactivity: Primary slicers for Year/Quarter and Location.

B. Operational Efficiency & Flow
Bed Management: Real-time (or near real-time) Bed Occupancy Rate and visualizations of patient flow across different units.

Bottleneck Analysis: Charts identifying departments or times of day with the highest Wait Times or longest ALOS.

Metrics: Focus on ALOS comparison by Diagnosis-Related Group (DRG).

C. Quality & Safety
Rate Tracking: Monitors Mortality Rate, Infection Rate, and the 30-day Readmission Rate.

Benchmarking: Compares internal department performance against system-wide or industry benchmarks.

Visuals: Scatter plots or matrices comparing Quality Score vs. Patient Volume.

4. How to View and Use the Dashboard
Software Requirement: You must have Power BI Desktop installed.

File Access: Download the Hospital Dashboard.pbix file from this repository.

Open: Double-click the file to launch it in Power BI Desktop.

Interaction: Use the visual slicers and filters (e.g., selecting a Department or a Discharge Status) to drill down into the data.

Customization: All measures and visuals are fully customizable within Power BI Desktop for analysts needing to adapt the report.

5. Technology Stack
Primary Tool: Microsoft Power BI Desktop

Data Sources: Assumed to be pulled from various Hospital Information Systems (HIS) or Electronic Health Records (EHR) via SQL/CSV.

Language: DAX (Data Analysis Expressions) for creating complex healthcare-specific measures (e.g., risk-adjusted rates).
