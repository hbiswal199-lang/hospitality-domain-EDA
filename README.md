# 🏨 Atliq Hospitality Analysis — Exploratory Data Analytics (EDA)

An end-to-end Exploratory Data Analysis project examining booking performance, revenue realization, room occupancy rates, customer review patterns, and platform distribution across Atliq Grands properties using Python.

---

## 📌 Project Overview
Atliq Hospitality operates luxury and business hotel properties across major metropolitan hubs in India (Delhi, Mumbai, Bangalore, and Hyderabad). This project analyzes historical operational data, booking logs, and aggregate metrics to diagnose occupancy trends, revenue bottlenecks, outlier behaviors, and channel efficiencies.

---

## 📂 Datasets Used
* **`fact_bookings.csv`**: Contains transaction-level booking records (dates, guests, room category, platform, ratings, booking status, generated vs. realized revenue).
* **`fact_aggregated_bookings.csv`**: Daily property-level room demand, capacity, and successful bookings.
* **`dim_hotels.csv`**: Property metadata including hotel name, property ID, category (Luxury vs. Business), and city.
* **`dim_rooms.csv`**: Room classification codes (RT1: Standard, RT2: Elite, RT3: Premium, RT4: Presidential).
* **`dim_date.csv`**: Calendar dimensions mapping dates to day types (Weekday vs. Weekend) and week numbers.
* **`new_data_august.csv`**: Incremental operational performance metrics for August.

---

## 🛠️ Data Cleaning & Preprocessing
* **Invalid Value Removal:** Cleaned anomalous records with negative guest counts (`no_guests <= 0`).
* **Outlier Capping via 3-Sigma Rule:** Filtered extreme outlier values in `revenue_generated` (values above $\mu + 3\sigma$) while preserving valid RT4 high-tier presidential suite revenues.
* **Missing Value Imputation:** Handled missing room capacities in aggregate booking records using median capacity (`25.0`).
* **Date Normalization:** Parsed heterogeneous date representations into standard Pandas datetime formats for seamless chronological merges.

---

## 🔍 Key Insights & Findings

* **Revenue Drivers by Geography:**
  * **Mumbai** is the largest revenue-generating market with over **₹66.85 Cr** realized, followed by Bangalore (**₹42.03 Cr**), Hyderabad (**₹32.51 Cr**), and Delhi (**₹29.44 Cr**).
* **Property Performance:**
  * **Atliq Exotica** generated the highest realized revenue (**₹32.02 Cr**), while **Atliq Seasons** recorded the lowest (**₹6.60 Cr**).
* **Occupancy Patterns:**
  * **Weekend vs. Weekday:** Occupancy increases sharply on weekends (**72.39%**) compared to weekdays (**50.90%**).
  * **City-level Occupancy:** **Delhi** achieved the highest overall occupancy rate (**61.61%**), followed by Hyderabad (58.14%), Mumbai (57.94%), and Bangalore (56.59%).
  * **Room Types:** Occupancy rates remain uniform across categories, with Presidential suites (`RT4`) slightly leading at **59.30%**.
* **Guest Ratings:**
  * **Delhi** properties hold the highest average guest rating (**3.78 / 5.0**), whereas **Bangalore** properties lag with an average score of **3.41 / 5.0**.
* **Distribution Channels:**
  * Bookings are heavily dominated by third-party aggregators, with the `others` category and `makeyourtrip` generating the largest share of booking volume and realized revenue.

---

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Core Libraries:** Pandas, NumPy, Matplotlib

---

## 📂 Repository Structure
```text
├── datasets/
│   ├── fact_bookings.csv
│   ├── fact_aggregated_bookings.csv
│   ├── dim_hotels.csv
│   ├── dim_rooms.csv
│   ├── dim_date.csv
│   └── new_data_august.csv
├── hotels_analysis.ipynb     # Jupyter notebook with complete analysis and charts
└── README.md                 # Project documentation
