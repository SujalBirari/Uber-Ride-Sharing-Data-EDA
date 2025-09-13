# Uber Ride Analytics Dashboard - 2024

## 🚗 Project Overview
This project provides an in-depth exploratory data analysis (EDA) of Uber ride-sharing operations in 2024. The dataset contains **148,770 ride bookings** across multiple vehicle types, capturing critical operational, financial, and customer-related metrics. The goal of this project is to uncover trends in booking patterns, ride success and cancellations, revenue streams, customer and driver experience, and operational efficiency. 

Link - https://www.kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard
---

## 📊 Objective
The objective of this EDA is to:
- Understand ride-sharing demand and supply patterns.
- Investigate ride completion and cancellation behavior.
- Analyze operational metrics such as trip duration, driver response times, and ride distances.
- Examine customer and driver ratings to identify experience patterns.
- Surface actionable insights for operations and business strategy.

All questions, graphs, and derivations are **included in the notebook**.

---

## 📝 Dataset Description

| Column Name | Description |
|-------------|-------------|
| Date | Date of the booking |
| Time | Time of the booking |
| Booking ID | Unique identifier for each ride booking |
| Booking Status | Status of booking (Completed, Cancelled by Customer, Cancelled by Driver, etc.) |
| Customer ID | Unique identifier for customers |
| Vehicle Type | Type of vehicle (Go Mini, Go Sedan, Auto, eBike/Bike, UberXL, Premier Sedan) |
| Pickup Location | Starting location of the ride |
| Drop Location | Destination location of the ride |
| Avg VTAT | Average time for driver to reach pickup location (minutes) |
| Avg CTAT | Average trip duration from pickup to destination (minutes) |
| Cancelled Rides by Customer | Customer-initiated cancellation flag |
| Reason for cancelling by Customer | Reason for customer cancellation |
| Cancelled Rides by Driver | Driver-initiated cancellation flag |
| Driver Cancellation Reason | Reason for driver cancellation |
| Incomplete Rides | Incomplete ride flag |
| Incomplete Rides Reason | Reason for incomplete rides |
| Booking Value | Total fare amount for the ride |
| Ride Distance | Distance covered during the ride (km) |
| Driver Ratings | Rating given to driver (1-5 scale) |
| Customer Rating | Rating given by customer (1-5 scale) |
| Payment Method | Method used for payment (UPI, Cash, Credit Card, Uber Wallet, Debit Card) |

---

## 🔧 Project Steps

### 1. Data Understanding
- Explored the **dataset structure**, checking rows, columns, datatypes, and missing values.
- Summarized distributions of numerical features (e.g., Booking Value, Ride Distance) and categorical features (e.g., Vehicle Type, Payment Method).
- Identified **key metrics** such as overall ride success rate (~66%) and cancellation patterns (~25% of rides).

### 2. Data Cleaning & Preprocessing
- Handled **missing values**:
  - Filled or imputed missing VTAT and CTAT with median values grouped by Vehicle Type.
  - Replaced missing ratings with median for analysis.
- Corrected **datatype inconsistencies** for date and time columns.
- Replaced **Unknown** for cancellations and incomplete rides reasons for easier analysis.

### 3. Univariate Analysis
- Examined **distribution of booking values**: observed most rides fall in the lower fare range, with some high-value outliers.
- Visualized **ride counts by vehicle type**: Go Mini and UberXL dominated the fleet.
- Analyzed **cancellation counts** and **rating distributions**, highlighting skew towards higher ratings for completed rides.

### 4. Bivariate Analysis
- Analyzed **Booking Value vs Ride Distance**: fare scales approximately linearly with distance across vehicle types.
- Examined **payment method vs revenue**: cashless transactions (UPI, credit/debit cards) accounted for the majority of revenue.
- Investigated **vehicle type vs ride completion rate**: UberXL and Premier Sedan had slightly higher completion rates, whereas Go Mini had higher cancellations.

### 5. Feature Engineering
- Created new features to enhance analysis:
  - `Month`, `DayOfWeek`, `Hour` extracted from booking date and time to identify peak demand intervals.
- These features helped identify patterns such as high cancellation risk for long rides during peak hours.

---

## 🔍 Sample Insights & Conclusions

1. **Demand Patterns**
   - Most bookings occurred between **5 PM - 9 PM**, indicating peak evening demand.
   - Downtown areas were hotspots for pickups and drop-offs.

2. **Cancellation Behavior**
   - **Customer cancellations** were often due to **long wait times** or **change of plan**, especially during peak hours.
   - **Driver cancellations** were mostly associated with **high VTAT** or **ride distance exceeding driver preference**.

3. **Customer & Driver Experience**
   - Ratings were generally high, but low ratings correlated with delayed driver arrivals and ride cancellations.
   - Cashless payments were associated with slightly higher customer ratings, possibly due to convenience.

4. **Revenue Insights**
   - UberXL and Premier Sedan contributed disproportionately to total revenue, despite fewer rides.
   - Cashless transactions (UPI, card) dominated revenue collection.

> All graphs, detailed derivations, and answers to the EDA questions mentioned above are present in the Jupyter Notebook.

---

## 🛠️ Tools Used
- Python (pandas, numpy, matplotlib, seaborn)
- Jupyter Notebook
- GitHub for version control and project hosting

---
