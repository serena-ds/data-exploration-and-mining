# Case Study 1: Discovering Behavioral Patterns in Online Retail Data
## Project Overview
This project involves association mining on a European online retail dataset to identify common purchase patterns. The results are intended to guide marketing, promotional strategies, and inventory management.

Python Libraries Used: **Numpy**, **Pandas**, **Matplotlib**, **Seaborn**

## Dataset
- File: `D1.csv`
- Records: 19,663 transactions
- Attributes: InvoiceNo, Description, Quantity, CustomerID, etc.

## Pre-processing
### Data Type Adjustments:
- Converted `InvoiceNo` and `CustomerID` to categorical.
- Converted `InvoiceDate` to `datetime`.
### Missing Data:
- Removed rows with missing descriptions.
- Retained missing `CustomerID` entries to account for guest checkouts.
### Outlier Handling:
- Excluded rows with `Quantity` as "0" or extreme outliers.
  
## Analysis
### Association Mining
1. Parameters:
+ min_support: 0.02
+ min_confidence: 0.2
2. Key Findings:
+ Strong association rules identified between items like LUNCH BAG BLACK SKULL and JUMBO BAG RED RETROSPOT.
+ Frequent co-purchases with JUMBO BAG PINK POLKADOT include JUMBO BAG RED RETROSPOT and LUNCH BAG RED RETROSPOT.
### Sequence Analysis
- Conducted using `InvoiceDate` to identify transaction sequences.
- Set thresholds: min_support at 2% and min_confidence at 10%.
  
## Insights
The information generated from this association task can assist the retail store manager in many advertising and marketing decisions.
- **Product Advertising**: Identify and promote products likely to be bought together. For example, rule 46 and 160 (in task 4) suggest that JUMBO BAG PINK POLKADOT is likely to be bought together with either LUNCH BAG BLACK SKULL. or with a set of LUNCH BAG RED RETROSPOT and JUMBO BAG RED RETROSPOT, however not very often. Therefore, they could run a promotion for these combos in order to encourage customers to buy more.
- **Pricing Decision**: Helps the store manager make pricing decisions based on purchase patterns. For instance, rule 164 suggests that customers who buy LUNCH BAG RED RETROSPOT and JUMBO BAG PINK POLKADOT are at 77% chances of buying JUMBO BAG RED RETROSPOT. This means that the manager is able to mark JUMBO BAG RED RETROSPOT at a higher price to increase in profit.
- **Targeted Marketing**: Avoid irrelevant product promotions by focusing on items with positive purchase correlations. For itemsets that have negative correlation, the store manager can avoid sending customers irrelevant information on the products that they do not want.

## Conclusion
The analysis reveals valuable patterns in customer purchasing behavior, which can be leveraged for improved decision-making in marketing and sales strategies.
