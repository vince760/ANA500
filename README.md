# ✈️ Exploring Airline Passenger Satisfaction and On-Time Performance  
### ANA500 – Micro Project #1  

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green)
![Numpy](https://img.shields.io/badge/Numpy-Scientific%20Computing-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-yellow)

---

## 🧠 Project Overview
This project explores how operational and service-related factors affect **airline passenger satisfaction** and **on-time performance**.  
The analysis uses **NumPy** and **Pandas** to clean, organize, and analyze flight-level data, focusing on relationships between **flight distance**, **travel class**, **departure delays**, and **overall satisfaction**.

---

## 🎯 Problem Statement
Airlines continuously aim to improve customer experience and operational efficiency.  
This project investigates:
> *What factors most strongly influence passenger satisfaction, and how do operational variables such as flight distance and departure delays impact overall customer experience?*

---

## 💡 Hypotheses

**Primary Hypothesis (H₁):**  
Longer flights and business-class travel are associated with **higher satisfaction levels** due to enhanced service quality.  

**Null Hypothesis (H₀):**  
There is **no relationship** between flight distance, class, or travel type and satisfaction.  

**Secondary Hypothesis (H₁b):**  
Shorter flights are more likely to experience **higher departure delays** due to tighter scheduling.  


---

## 🧩 Dataset

| Feature Category | Example Columns | Description |
|------------------|-----------------|-------------|
| **Demographics** | `Gender`, `Age`, `Customer Type` | Passenger info |
| **Travel Details** | `Class`, `Type of Travel`, `Flight Distance` | Flight context |
| **Service Ratings** | `Inflight wifi service`, `Baggage handling`, `Checkin service` | Customer feedback (1–5 scale) |
| **Operational** | `Departure Delay in Minutes`, `Arrival Delay in Minutes` | Timeliness metrics |
| **Target Variable** | `Satisfaction` | Binary (Satisfied / Neutral or Dissatisfied) |

**Dataset Size:** ~129,000 rows  
**Source:** Airline Passenger Satisfaction dataset (Kaggle / course-provided file)

---

## 🧹 Data Preparation
- Encoded categorical variables into numeric values  
- Handled missing data (`Arrival Delay in Minutes` → replaced NaNs with 0)  
- Detected and adjusted outliers in `Flight Distance` using the IQR method  
- Created a capped variable `Flight Distance_Adjusted`  
- Verified data integrity and consistency  

---

## 📊 Exploratory Analysis & Visualizations
Key insights were drawn using Pandas and Matplotlib/Seaborn visualizations:

| Visualization | Purpose |
|----------------|----------|
| **Boxplot of Flight Distance** | Identify and cap outliers |
| **Bar Chart – Satisfaction by Class** | Compare satisfaction across cabin types |
| **Line Chart – Average Delay by Distance Range** | Observe operational efficiency trends |
| **Heatmap – Class vs. Travel Type** | Examine combined effects on satisfaction |

Example:
```python
plt.figure(figsize=(10,5))
avg_delay_by_distance.plot(kind='line', marker='o', color='royalblue')
plt.title("Average Departure Delay by Flight Distance")
plt.xlabel("Distance Range (miles)")
plt.ylabel("Average Delay (minutes)")
plt.grid(True)
plt.show()
