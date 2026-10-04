Sales and Profitability Review
A Power BI portfolio project exploring which products and markets generate substantial sales but weaker profit margins, and where a stakeholder should investigate costs, pricing or discounts.
 
Tools
- Power BI Desktop for the report and interactive filtering.
- Power Query for data preparation and calculated columns.
- DAX for totals and weighted financial ratios.

Data and scope
Source: Microsoft Financial Sample Excel workbook.
The sample contains 700 records across six products, five countries and five segments, covering September 2013 through December 2014. This is sample data for a portfolio project and does not describe Tourmaline's operations. Dollar amounts follow the sample's notation and are not identified as CAD.

Data preparation
- Set appropriate text, date and numeric types, and trimmed categorical values.
- Kept Units Sold as a decimal to preserve fractional quantities.
- Checked column quality for errors and missing values.
- Created Month Start with Date.StartOfMonth([Date]) to preserve month and year when grouping.
- Created Profit Difference with ([Sales] - [COGS]) - [Profit] and corrected a field-reference error using the actual source column names.
- Retained all products and negative profits, without deleting repeated-looking records as presumed duplicates.

Measures
Total Sales = SUM(Financials[Sales])
Total Profit = SUM(Financials[Profit])
Total Gross Sales = SUM(Financials[Gross Sales])
Total Discounts = SUM(Financials[Discounts])
Profit Margin = DIVIDE([Total Profit], [Total Sales])
Discount Rate = DIVIDE([Total Discounts], [Total Gross Sales])
Ratios use totals within the selected filter context rather than averages of individual row percentages.

Overall results
Results include all 700 records with filters and chart selections cleared.
KPI	- Result
Total Sales -	$118,726,350.26
Total Profit -	$16,893,702.26
Profit Margin -	14.2%
Discount Rate	- 7.2%


Findings
- Product: Velo ranks third in sales at $18.25 million but has the lowest product margin at 12.6% and the highest product discount rate at 8.0%.
- Segment: Enterprise generates $19.61 million in sales but loses approximately $614,546. Its 6.9% discount rate is below the overall rate, so discounts alone do not explain its loss.
- Market: The United States has the highest country sales at $25.03 million, the lowest country margin at 12.0%, and the highest country discount rate at 8.2%.
- Month: December 2014 has the highest profit at $2.03 million, while November 2014 has the lowest at approximately $604,600. October 2014 has the highest sales.
Stakeholder takeaway
Velo generated $18.25 million in sales with the lowest product margin of 12.6%, while the Enterprise segment lost approximately $614,546 despite $19.61 million in sales. A stakeholder should prioritize reviewing Velo's pricing and discounts and Enterprise's cost of goods sold and product mix, using country and year filters to narrow the investigation.


Validation and limitations
An independent calculation from the original sample confirms that Sales - COGS - Profit and Gross Sales - Discounts - Sales equal zero for every record. The full sample totals above provide a baseline for checking the dashboard.
Profit equals Sales minus COGS and excludes other operating expenses. Discount comparisons show associations rather than causation. The dataset contains only four months for 2013, so full-year totals are not directly comparable with 2014, and recurring seasonality cannot be established.


Files and opening instructions
- Sales-Profitability-Review.pbix: Power BI project.
- dashboard-preview.png: report screenshot.
- Sales-Profitability-Project-Report.docx: detailed methodology, findings and recommendations.
- README.md: project overview.
Download Sales-Profitability-Review.pbix and open it in Power BI Desktop to explore the saved report. To refresh from Excel, download the source workbook linked above and update the source file path under Transform data > Data source settings if needed.
