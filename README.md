# Gen-AI-Assignment
# E-Commerce Customer Review Analysis & AI-Powered Customer Support

## Overview

This project demonstrates an end-to-end workflow for processing and analyzing e-commerce customer reviews using **Python**, **Pandas**, **rule-based text analysis**, and **Generative AI**.

The project begins with a raw synthetic e-commerce dataset containing customer information, order details, ratings, and text reviews. The data is cleaned and standardized using Pandas, after which critical customer reviews are identified using rule-based filtering.

The most common complaint keywords are then extracted and visualized to identify recurring customer issues. Finally, selected critical reviews are passed to the **Google Gemini API**, which acts as a customer support agent and generates personalized apology responses based on the customer's complaint.

---

## Project Objectives

The project is divided into three main stages:

1. **Data Wrangling and Cleaning**
2. **Rule-Based Filtering and Complaint Analysis**
3. **Generative AI-Powered Customer Outreach**

---

## Dataset

The project uses a synthetic e-commerce customer review dataset containing **2,500 records**.

### Dataset Columns

| Column | Description |
|---|---|
| `Order_ID` | Unique identifier for each order |
| `Cust_ID` | Unique identifier for each customer |
| `Prod_ID` | Unique identifier for each product |
| `Cust_Name` | Customer's full name |
| `City` | Customer's city |
| `Order_Date` | Date on which the order was placed |
| `Email` | Customer's email address |
| `Amount` | Order amount |
| `Review` | Customer's text review |
| `Ratings` | Customer rating from 1 to 5 |
| `Delivery_Date` | Date on which the order was delivered |

The raw dataset intentionally contains several data-quality issues to simulate a real-world data-cleaning workflow.

These include:

- Missing values in `City`
- Missing values in `Cust_Name`
- Missing values in `Amount`
- Inconsistent capitalization of city names
- Text data requiring standardization
- Customer reviews associated with different rating levels

---

# 1. Data Wrangling and Cleaning

The first stage of the project focuses on inspecting and cleaning the raw dataset using **Pandas**.

## Data Loading

The dataset is loaded into a Pandas DataFrame:

```python
import pandas as pd

df = pd.read_csv("synthetic_ecommerce_reviews_2500.csv")
