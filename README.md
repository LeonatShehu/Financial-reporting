# Financial Reporting Dataset

Financial dataset of **220 transactions across 7 Kosovo cities**, built in Excel for **financial reporting, budget-vs-actual analysis and profit & loss (P&L) summaries**.

<!-- [<img width="1126" height="650" alt="Screenshot 2026-10-01 at 14 34 05" src="https://github.com/user-attachments/assets/d4483aaf-63b2-43ed-9983-2775c0457709" />
](<img width="740" height="653" alt="Screenshot 2026-10-01 at 14 33 58" src="https://github.com/user-attachments/assets/9744b626-c927-4030-ae8c-4922a53f4be8" />
) -->

---

## What's included

| Sheet | Description |
|---|---|
| **README** | Definitions, assumptions and notes |
| **Transactions** | 220 rows of revenue, cost of goods sold (COGS) and operating expenses with budget vs. actual |
| **P&L_Summary** | Monthly profit & loss (January–September 2026), total vs. budget, margins and a chart |
| **By_Department** | Actual results by department and by city |

### Transactions columns

| Column | Description |
|---|---|
| `Txn_ID`, `Date` | Transaction ID and date (1 Jan – 30 Sep 2026) |
| `Month`, `Quarter` | Calculated from the date (formulas) |
| `City` | Prishtina, Prizren, Peja, Gjakova, Mitrovica, Ferizaj or Gjilan |
| `Department` | Sales, Marketing, Operations, Finance, HR, IT, Customer Support |
| `Account_Type`, `Account` | Revenue / COGS / Operating Expense, and the specific account (e.g. Product Sales, Rent, Software & Licenses) |
| `Description`, `Customer_Vendor` | Transaction description and the (fictitious) counterparty |
| `Budget (€)`, `Actual (€)` | Budgeted and actual amounts |
| `Variance (€)`, `Variance %` | Favorable when positive (formulas) |
| `Result` | Favorable / Unfavorable / On budget (within ±2%) |
| `Signed_Amount (€)` | Positive for revenue, negative for costs |
| `Payment_Status` | Paid, Pending or Overdue |

---

## Summary of the data

| | Rows | Actual (€) |
|---|---|---|
| Revenue | 72 | 1,373,370 |
| COGS | 48 | 475,000 |
| Operating expenses | 100 | 851,550 |
| **Operating income** | | **46,820** (3.4% margin) |

Operating income is below the budgeted total of €82,540. Prishtina accounts for the most transactions (80 of 220), reflecting its larger economy.

---

## How it works

- Input data (blue font) is in `Transactions`. Everything else is formulas (about 1,500 in total), so the P&L and department/city tables update when you edit the data.
- The P&L uses `SUMIFS` on `Account_Type` and the month.
- **Variance** is `Actual − Budget` for revenue and `Budget − Actual` for costs, so a positive variance is always favorable.
- **Budget** was simulated as the actual amount multiplied by a random factor between 0.82 and 1.18.

---

## Limitations

- Departments and accounts are assigned independently, so combinations such as Marketing costs booked under IT can appear.
- Because the data is random, some cities and departments show losses. This is not a real-world pattern.
- Amounts do not include VAT (18% in Kosovo) and there is no balance sheet or cash flow.
- Budgets are simulated and are not based on real planning.

---

## Possible extensions

- Add VAT, receivables and payables aging
- Link accounts to the correct departments
- Add a balance sheet and cash-flow statement
- Add more months to analyze trends and seasonality

---

## Repository structure

```
.
├── Financial_Reporting_Kosovo.xlsx
├── images/            # screenshots (optional)
└── README.md
```
