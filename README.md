
---

### 📌 **Starbucks Pricing Analysis Project**  
**By Evidence Madhume**  

---

## 📌 **Project Overview**  
This project investigates **customer spending patterns and price sensitivity** in the **Starbucks Rewards Program**, focusing on **correcting selection bias** in price elasticity estimates. The analysis leverages **log-log regression, Heckman selection correction, Polynomial Regression, and Random Forest models** to provide **data-driven insights for pricing strategies and revenue optimization**.

---

## 🎯 **Business Objectives**  
✅ **Accurately estimate price elasticity** while accounting for selection bias.  
✅ **Understand customer spending behavior** by age, gender, and loyalty enrollment status.  
✅ **Optimize pricing strategies** based on refined model predictions.  
✅ **Quantify revenue loss estimates** under biased vs. corrected models.  

---

## 📂 **Project Structure**  
```
Pricing-Analysis-Starbucks/
│── data/                      <- Raw and processed data files.
│── images/                    <- Visualizations and insights.
│── notebooks/                 <- Jupyter Notebooks and RMarkdown.
│── src/                       <- Python and R scripts.
│── README.md                  <- Project documentation.
│── requirements.txt           <- Dependencies for running the project.
```
---

---

## 🔍 **Exploratory Data Analysis (EDA)**  

EDA was conducted to **understand customer spending patterns**, **detect missing values**, and **identify outliers** before model training.  

### 🛠 **1. Data Cleaning & Preprocessing**  
- **Missing Values:** Checked and handled appropriately.  
- **Duplicates:** Removed from the dataset to avoid redundancy.  
- **Outliers:**  
  - **Monthly Spend** was **capped at the 95th percentile** to prevent extreme values from skewing results.  
  - **Average Price** outliers were identified using the **IQR method** and replaced with the mean.  

### 📊 **2. Descriptive Statistics**  
| Variable               | Min | 25%  | 50%  | 75%  | Max |
|------------------------|-----|------|------|------|-----|
| Monthly Spend (USD)    | 5.2 | 18.3 | 29.5 | 45.6 | 200.0 |
| Average Price (USD)    | 1.8 | 3.2  | 4.5  | 5.8  | 7.5 |
| Customer Age (years)   | 18  | 24   | 32   | 42   | 65  |

---

### 📈 **3. Data Visualization Insights**  

#### **📌 Monthly Spending Distribution**  
Most customers spend **between $18-$46 per month**, while a few **outliers exceed $200**.  

![Monthly Spend](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Monthly_Spend_Distribution.png)

#### **📌 Average Price Distribution**  
- Prices follow a normal distribution.  
- The **most common coffee price is around $4.5**, with few stores charging above $7.  

![Price Distribution](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Price_Distribution.png)

#### **📌 Gender-Based Spending Behavior**  
- **Female customers** spend significantly **more than male customers**.  
- The **spending distribution skews higher** for female customers.  

![Gender Spend](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Gender_Spending.png)

#### **📌 Correlation Analysis**  
- **Monthly Spend is negatively correlated with Average Price (-0.68)**  
- **Older customers tend to spend more** on coffee.  
- **Enroll Promo Value** affects spending **positively**, suggesting **loyalty incentives work**.  

![Correlation Matrix](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Correlation_Matrix.png)

---

## 📊 **Key Findings**  

### 📌 **Model Comparison Summary**  

| Model         | Price Coefficient | p-value (Price) | Adjusted R² | AIC    | BIC    | MSE    |
|--------------|------------------|----------------|-------------|--------|--------|--------|
| **Baseline**  | -1.79            | < 2e-16 ***    | 0.5676      | 7541.98 | 7572.14 | 0.7742 |
| **Polynomial** | -2.14            | < 2e-16 ***    | 0.7039      | 6920.85 | 6957.05 | 0.5302 |

📌 **A small p-value (<0.05) confirms that price strongly impacts customer spending.**  

---

### 📌 **1. Price Sensitivity & Revenue Loss**  
- **Baseline Model:** Estimated price elasticity of **-1.79**, meaning a **1% price increase results in a 1.79% decrease** in monthly spending.  
- **Polynomial Model (Corrected):** Price elasticity **increases to -2.14**, meaning **a 1% price increase leads to a 2.14% decrease** in spending.  
- **Revenue Loss Projection:** The **corrected model predicts higher revenue losses**, indicating that ignoring selection bias could lead to overly aggressive pricing strategies.

**Revenue Loss Comparison:**  
![Revenue Loss](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Revenue_Loss_Comparison.png)

---

### 📌 **2. Customer Spending Behavior**  
- **Age Impact:** Older customers spend **1.11% more** per additional year.  
- **Gender Impact:** **Female customers spend 5.96 times more** than male customers, making them high-value targets for promotions.  

**Spend by Enrollment Status:**  
![Spend by Enrollment](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Monthly_Spend_by_Enrollment.png)

---

### 📌 **3. Selection Bias in Pricing Models**  
- **Loyalty program customers are less price-sensitive** than the general population.  
- **Ignoring selection bias leads to underestimating price elasticity**, which can cause **incorrect pricing decisions and revenue loss**.  

**Heckman Selection Model (Corrected):**  
### Regression Model Summary (With Enrollment Correction)

| Variable          | Estimate  | Std. Error | t value | p value        |
|------------------|-----------|------------|--------|----------------|
| (Intercept)      | 6.50       | 0.14        | 45.69   | < 2e-16 ***     |
| log_avgPrice     | -2.13      | 0.07        | -29.20  | < 2e-16 ***     |
| age              | 0.01       | 0.00        | 8.64    | < 2e-16 ***     |
| female           | 1.96       | 0.03        | 73.90   | < 2e-16 ***     |
| predicted_enroll | -2.33      | 0.06        | -37.33  | < 2e-16 ***     |

---

### 📌 **4. Best Model: Polynomial Regression**  
- **Best Adjusted R² (0.7039) → Most accurate in predicting customer behavior.**  
- **Price Coefficient: -2.14 → Strongest impact of pricing on demand.**  

**Polynomial Model Summary:**  
| Variable             | Estimate  | Std. Error | t value | p value        |
|---------------------|-----------|------------|--------|----------------|
| (Intercept)         | 6.56       | 0.14        | 46.05   | < 2e-16 ***     |
| log_avgPrice        | -2.14      | 0.07        | -29.39  | < 2e-16 ***     |
| age                 | 0.01       | 0.00        | 8.83    | < 2e-16 ***     |
| female              | 1.96       | 0.03        | 74.25   | < 2e-16 ***     |
| predicted_enroll_poly | -2.41      | 0.06        | -37.63  | < 2e-16 ***     |

---

## 📌 **Business Implications & Strategic Recommendations**  

### 🔹 **1. Data-Driven Pricing Strategy**  
✔ **Use the Polynomial Model** for pricing decisions as it provides the most accurate **price elasticity estimates.**  
✔ **Avoid aggressive price hikes** to minimize **customer churn risk.**  

### 🔹 **2. Targeted Marketing & Promotions**  
✔ **Female customers are high-value spenders** – prioritize engagement through **exclusive promotions.**  
✔ **Older customers** respond well to **loyalty incentives**, driving **higher retention.**  

### 🔹 **3. Revenue Optimization**  
✔ **Introduce regional price adjustments** based on **demographic spending behavior.**  
✔ **Use strategic discounts** for high-price-sensitive customers to **maximize revenue without excessive churn.**  

---

## 📩 **Connect With Me**
📧 **Email:** emadhume@smu.edu  
🔗 **LinkedIn:** [LinkedIn](https://www.linkedin.com/in/evidence-madhume-874540204/)  
🌍 **GitHub**: [EvidenceM290](https://github.com/EvidenceM290)  

---
