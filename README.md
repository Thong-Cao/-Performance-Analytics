<h1 align="center">
  <br>
  <span style="color: #2E86C1;">Top-Up Service Performance Analysis</span>
  <br>
</h1>
<h4 align="center">
  <span style="color: #28B463;">Transforming Data Into Valuable Insights For Strategic Growth</span>
</h4>

## Overview

This project analyzes the performance of a **top-up service** provided by **e-wallet companies**. These services allow users to add money to their e-wallets, and the e-wallet providers earn commissions from Telco merchants for each transaction.
This is a personal project to showcase my data processing and visualization skills, identifying key performance indicators (**KPIs**) and deriving insights from the dataset.

### Analysis Steps:
1. **Exploring the dataset:** Understanding the business model and all dataset fields.
2. **Defining problems:** Identifying the KPIs for performance tracking based on the entire dataset.
3. **Data processing:** Using **Python (Pandas DataFrame)**.
4. **Data visualization:** Utilizing **Power BI**.
5. **Analysis and insights**.

## Data Exploration

The top-up service data includes daily transactions (table '**Transactions**'), user demographic information (table '**User_info**'), and the commission percentage paid by Telco merchants (table '**Commission**').

<div style="display: flex; justify-content: space-between;">

<div>

### Transactions:

| **Field**           | **Description**                                  |
|---------------------|--------------------------------------------------|
| User_id           | Unique ID for each user                          |
| Order_id          | Unique ID for each transaction                   |
| Date              | Date of the transaction                          |
| Amount            | Transaction amount (VND)                         |
| Merchant_id       | Unique ID for each merchant                      |
| Purchase_status   | Label 'Mua hộ' if the user buys a card for another user |

</div>

<div>

### Commission:

| **Field**           | **Description**                                  |
|---------------------|--------------------------------------------------|
| Merchant_name     | Telco name                                       |
| Merchant_id       | Unique ID for each merchant                      |
| Rate_pct          | Commission percentage (%) for each transaction amount |

</div>

<div>

### User_Info:

| **Field**           | **Description**                                  |
|---------------------|--------------------------------------------------|
| User_id           | Unique ID for each user                          |
| First_tran_date   | First day of using the top-up service            |
| Gender            | Male/Female                                      |
| Age               | Age groups                                       |
| Location          | Location on the ID card                          |

</div>

</div>


## Problem Statements

Before the analysis, I explored the data to gain a comprehensive understanding. From this exploration, I defined the following problems to solve:

1. What is the **monthly transaction count** and **revenue**?
2. Which locations have the **most transactions**?
3. Which Telco merchant dominates the **top-up market in Vietnam**, and which denominations are **most popular**?
4. What is the **total number of users**, and how many are **new versus returning users**?

### KPIs for Analysis:

- **📊 Total Transactions:** **Count of `Order_id`**
- **💰 Total Revenue:** **Sum of `Amount` * `Rate_pct` per transaction**
- **🛒 Total Sales:** **Sum of all `Amount`**
- **📈 Revenue per Transaction:** **Total Revenue / Total Transactions**
- **⚖️ %Revenue:** **Total Revenue / Total Sales**
- **👥 Total Users:** **Distinct count of `User_id`**
- **🔄 New/Current Users:** **Identified based on `First_tran_date` and transaction dates**
- **💵 Sales/Revenue per User:** **(Total Sales/Total Revenue) / Total Transactions**

  
## Data Processing

Based on the defined KPIs, data processing involves checking for null values, duplicate data, and standardizing columns. The notebook `DataProcessing.ipynb` details the data processing steps, including:
- Checking for **null values** and **duplicates**
- Processing **dates columns**
- Creating **derived columns** such as `[month]`, `[Day_of_Week]`, `[Revenue]`, and `[Type_user]`
- Standardizing the `[Gender]` and `[Location]` columns

## Data Visualization

Using **Power BI** for data visualization to track performance and user demographics:
![chart1](img/img1.png)
![chart2](img/img2.png)
