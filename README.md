# hospital-patients-dashboard
Hospital patient data analysis and Excel dashboard 

SECURELIFE GENERAL HOSPITAL 

Secure Life General Hospital's management had seen admissions, unpaid bills and insurance coverage shift across departments, but had no single report of operational and financial performance. As the data analyst, I turned the raw visit data into an interactive Excel dashboard that answers ten management questions and adds insights beyond them.

Data

The dataset has 1,000 rows, one per patient visit, with admissions in 2024 and 2025 across six departments: Cardiology, Emergency, General, Neurology, Orthopedics and Pediatrics. Each row records patient ID, name, age, gender, admission and discharge dates, department, diagnosis, total bill, insurance coverage (%) and payment status. Only 684 distinct names appear, so patients return more than once; I therefore report visits, not unique patients.

Cleaning and analysis

The source data had no blank values and no negative stays, so most of the work was feature engineering. I added columns that were not in the original data so management's questions could be answered directly:


How I built it


Age category =
Excel (IFS formula grouping age into under 18, 18 to 35, 36 to 50, 51 to 66 and 66 and above)


Length of stay (days) = 
(Discharge date minus admission date for each visit; averaged by department in a PivotTable)

Average stay across departments (4.8 days overall)

Paid Amount = 
(SUMIF on bills with payment status Paid)


I then built PivotTables for each measure and linked them to slicers for year, department and diagnosis, so every chart responds to the same filters.

The dashboard


The dashboard opens with headline tiles: 1,000 visits, $8.05M billed, 4.8 days average stay and 74.9% average insurance coverage.

Below them are five views: admission trend by month and quarter, visits by department, visits by age group, payment status and visits by gender. 

Slicers for year, department and diagnosis let management filter all views at once.

Key findings

Orthopedics and Cardiology produce 58% of the $8.05M billed from only 31% of visits, and unpaid bills are a large share of revenue.


• Payments: 564 visits (56.4%) are fully paid, 257 (25.7%) are pending, worth $2.08M, and 179 (17.9%) are partially paid, worth $1.40M.

• Insurance: coverage averages 74.9% and varies little by department, from 73.9% to 76.3%.

• Age: the 51 to 66 group has the most visits (235), followed by 66 and above (220).

• Trend: admissions were steady, 508 in 2024 and 492 in 2025, with monthly counts between 29 and 57.

Recommendations
1. Chase pending bills first. Start a follow-up routine for the 257 pending visits ($2.08M), beginning with the largest bills.
2. Review Orthopedics stays. At 8.4 days, the average is 1.7 times the hospital's 4.8 days; check discharge planning and bed use.
3. Check Emergency billing. It is the second-busiest department but bills only $0.62M for 2-day stays; confirm charges are fully captured.
4. Look beyond coverage. Insurance cover is flat at about 75%, so differences in payment status probably come from patient balances and collection, not from insurers.

   
Tools, limitations and next steps

Tools: Microsoft Excel (IFS, SUMIF, PivotTables, slicers, charts).

Limitations

• Each Patient ID is unique per visit, so repeat patients can only be linked by name.

• Patient names sit in the source sheet; the dashboard shows none, and I would remove them before sharing the workbook.

• Payment status does not say how much of a partially paid bill was settled, so outstanding amounts are an upper bound ($3.48M for pending plus partially paid).
