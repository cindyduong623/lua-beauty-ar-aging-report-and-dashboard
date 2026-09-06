# lua-beauty-ar-aging-report-and-dashboard
Excel AR aging schedule and interactive Power BI dashboard for fictional Vietnamese beauty brand
# Lụa Beauty: Accounts Receivable Aging Report & Dashboard

## About This Project
Lụa Beauty is a fictional Vietnamese beauty brand that sells skincare and cosmetics wholesale to boutiques, spas, and salons. This project replicates a standard AR aging workflow: extracting raw invoice data, executing data cleaning, generating an Excel aging schedule, and building an interactive Power BI dashboard.

## Process

**1. Raw Data**
Started with 52-row invoice export containing realistic data issues: different date formats, inconsistent customer name capitalization and spacing, missing information, duplicate invoices, and a negative amount

**2. Data Cleaning**
Standardized dates and customer names using PROPER, TRIM, and SUBSTITUTE (to handle apostrophes) and identified duplicate rows using Conditional Formatting (Highlight Duplicate Values) and manual inspection

**3. Aging Calculations**
Built formulas using arithmetic, IF, and IFS for Balance Due, Days Past Due, and Aging Bucket (Paid, Current, 1-30, 31-60, 61-90, 90+ Days)

**4. Aging Summary**
Built a table summarizing Balance Due by Customer and Aging Bucket using SUMIFS, tied out against the Cleaned Data total (credit memo withstanding)

**5. Power BI Dashboard**
Loaded the cleaned data into Power BI and built summary cards for Total AR Outstanding and Total 61-90 Days Past Due, a stacked bar chart flagging risk by age, a matrix (Customer x Aging Bucket), Customer and Aging Bucket slicers, and a customer totals table

## Notes
- **Credit memo (–$410, Orchid Lane Boutique):** nets against the customer's balance but is excluded from the aging buckets since it has no positive balance to age
- **90+ Days bucket is empty** by construction as no invoice in this sample is 90 days past due.
- **Removed two hidden duplicate invoices** found after initial "Highlight Duplicate Values" round because of blank cells (one blank customer name, one blank invoice amount)

## Files
- `Lua Beauty AR Aging Report.xlsx`: Excel workbook (Raw Data, Cleaned Data, Aging Summary)
- `Lua Beauty AR Aging Dashboard.pbix`: Power BI dashboard
