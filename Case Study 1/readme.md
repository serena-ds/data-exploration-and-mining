# Case Study 1: Discovering Behavioral Patterns in Online Retail Data
## Project Overview
This project involves association mining on a European online retail dataset to identify common purchase patterns. The results are intended to guide marketing, promotional strategies, and inventory management.

## Dataset
- File: `D1.csv`
- Records: 19,663 transactions
- Attributes: InvoiceNo, Description, Quantity, CustomerID, etc.

## Pre-processing
### Data Type Adjustments:
- Converted InvoiceNo and CustomerID to categorical.
- Converted InvoiceDate to datetime.
### Missing Data:
- Removed rows with missing descriptions.
- Retained missing CustomerID entries to account for guest checkouts.
### Outlier Handling:
- Excluded rows with Quantity as "0" or extreme outliers.
  
## Analysis
### Association Mining
- Parameters:
+ min_support: 0.02
+ min_confidence: 0.2
- Key Findings:
+ Strong association rules identified between items like LUNCH BAG BLACK SKULL and JUMBO BAG RED RETROSPOT.
+ Frequent co-purchases with JUMBO BAG PINK POLKADOT include JUMBO BAG RED RETROSPOT and LUNCH BAG RED RETROSPOT.
### Sequence Analysis
- Conducted using InvoiceDate to identify transaction sequences.
- Set thresholds: min_support at 2% and min_confidence at 10%.
  
## Insights
The information generated from this association task can assist the retail store manager in many advertising and marketing decisions.

Firstly, it helps to identify what type of products should be advertised together. For example, rule 46 and 160 (in task 4) suggest that JUMBO BAG PINK POLKADOT is likely to be bought together with either LUNCH BAG BLACK SKULL. or with a set of LUNCH BAG RED RETROSPOT and JUMBO BAG RED RETROSPOT, however not very often. Therefore, they could run a promotion for these combos in order to encourage customers to buy more.

Secondly, it helps the store manager make pricing decisions. For instance, rule 164 suggests that customers who buy LUNCH BAG RED RETROSPOT and JUMBO BAG PINK POLKADOT are at 77% chances of buying JUMBO BAG RED RETROSPOT. This means that the manager is able to mark JUMBO BAG RED RETROSPOT at a higher price to increase in profit.
Moreover, it can help the store manager in targeting the right customers when they send advertising emails. For itemsets that have negative correlation, the store manager can avoid sending customers irrelevant information on the products that they do not want. Instead, we can focus on the products that are likely to be bought together and suggest them when the customer is checking out.

## Conclusion
The analysis reveals valuable patterns in customer purchasing behavior, which can be leveraged for improved decision-making in marketing and sales strategies.
