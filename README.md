# Item Code Separation and Price Lookup
![vlookup](https://github.com/amadigodswill33/DataOrganizationProject/assets/94016023/842a4fda-53ee-4334-8c14-486918c9756f)

## Overview

This project aimed to enhance the organization and structure of product data by separating item codes from the product names. The process involved the extraction of item codes, lookup of corresponding prices, and standardization of the Master Sheet.

## Table of Contents

1. [Objective](#objective)
2. [Implementation Steps](#implementation-steps)
   - [Item Code Separation](#item-code-separation)
   - [Price Lookup](#price-lookup)
   - [Data Standardization](#data-standardization)
3. [Formulas Used](#formulas-used)
   - [Formula 1](#formula-1)
   - [Formula 2](#formula-2)
   - [Formula 3](#formula-3)
4. [Project Success](#project-success)

## Objective

The primary goal of this project was to improve data organization and facilitate analysis by separating item codes from product names, looking up corresponding prices, and standardizing the Master Sheet.

## Implementation Steps

### Item Code Separation

To achieve item code separation, the following steps were implemented:

1. Utilized the formula below to identify and extract item codes within parentheses:
   ```
   =IFERROR(IF(AND(ISNUMBER(FIND("(", A3)), MID(A3, FIND("(", A3) + 1, 1) = "8"), MID(A3, FIND("(", A3) + 1, FIND(")", A3) - FIND("(", A3) - 1), ""), "")
   ```
2. Employed a SUBSTITUTE function to replace item codes in the product name field:
```
=IF(ISNUMBER(SEARCH("(8", A3)), SUBSTITUTE(A3, MID(A3, SEARCH("(", A3), IFERROR(SEARCH(")", A3, SEARCH("(", A3) + 1) - SEARCH("(", A3), LEN(A3))), ""), A3)
```
### Price Lookup
Integrated corresponding prices for each item code from an external Excel sheet containing item codes and prices.
```
=IFERROR(VLOOKUP(C3, SEGEL!C5:F395, 3, FALSE), "")
```
### Data Standardization
Formatted the Master Sheet to ensure a standardized and organized structure for improved accessibility and user-friendliness.

## Formulas Used
Formula 1
```
=IFERROR(IF(AND(ISNUMBER(FIND("(", A3)), MID(A3, FIND("(", A3) + 1, 1) = "8"), MID(A3, FIND("(", A3) + 1, FIND(")", A3) - FIND("(", A3) - 1), ""), "")
```
Formula 2
```
=IF(ISNUMBER(SEARCH("(8", A3)), SUBSTITUTE(A3, MID(A3, SEARCH("(", A3), IFERROR(SEARCH(")", A3, SEARCH("(", A3) + 1) - SEARCH("(", A3), LEN(A3))), ""), A3)
```
Formula 3
```
=IFERROR(VLOOKUP(C3, SEGEL!C5:F395, 3, FALSE), "")
```
---
## Project Success
The project was highly successful in achieving its objectives. The item codes were effectively separated from product names, prices were accurately looked up and integrated, and the Master Sheet was standardized for improved data management and analysis.
![newFile_Preprocessed](https://github.com/amadigodswill33/DataOrganizationProject/assets/94016023/b7509ae9-e372-40ee-b501-3a8c39cbd23a)
