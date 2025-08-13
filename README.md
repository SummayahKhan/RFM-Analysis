# RFM-Analysis
# RFM Customer Segmentation Analysis

This project performs **RFM (Recency, Frequency, Monetary) analysis** on a customer dataset to segment customers and visualize their distribution. It includes data cleaning, calculation of RFM scores, customer segmentation, and visualizations (bar chart & treemap).

---


## Project Structure



## **Dataset**

- `eco.csv` contains transaction data with the following columns:  
  - `CustomerID` : Unique identifier for each customer  
  - `InvoiceNo` : Invoice/Order number  
  - `InvoiceDate` : Date of transaction  
  - `StockCode` : Product code  
  - `Quantity` : Quantity purchased  
  - `UnitPrice` : Price per unit  

> Note: Data should be cleaned to remove duplicates, missing CustomerIDs, and negative/zero quantities.

---

## **Steps in Analysis**

1. **Data Cleaning**  
   - Convert `InvoiceDate` to datetime  
   - Remove duplicates  
   - Remove rows with missing or blank `CustomerID`  
   - Remove negative or zero quantities and unit prices  
   - Calculate `Revenue = Quantity × UnitPrice`  

2. **RFM Calculation**  
   - **Recency**: Days since last purchase  
   - **Frequency**: Number of unique invoices per customer  
   - **Monetary**: Total revenue per customer  
   - Normalize last purchase date and compute `Recency` relative to dataset max date  

3. **RFM Scoring**  
   - Recency: Lower is better → higher score for more recent purchases  
   - Frequency & Monetary: Higher is better → higher score for larger values  
   - Scores assigned using `pd.qcut` into 5 levels (1–5)  

4. **Customer Segmentation**  
   - Assign each customer to segments such as **CHAMPION**, **LOYAL CUSTOMER**, **NEW CUSTOMER**, **AT RISK**, etc., based on R, F, M scores  

5. **Visualization**  
   - **Bar Chart**: Count of customers per segment  
   - **Treemap**: Visual representation of customer distribution by segment using `squarify`  

---

## **Dependencies**

```txt
numpy
pandas
matplotlib
squarify
