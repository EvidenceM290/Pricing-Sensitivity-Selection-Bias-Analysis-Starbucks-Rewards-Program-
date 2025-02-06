### 📌 **Pricing Sensitivity & Selection Bias Analysis (Starbucks Rewards Program)**
---

## 🔍 **Project Overview**
This project analyzes **customer spending behavior and price sensitivity** in Starbucks’ **loyalty program** using **log-log regression models, Heckman selection correction, and machine learning techniques (Random Forest, Polynomial Regression).** The study corrects for **selection bias**, ensuring accurate **price elasticity estimates** and optimal **pricing strategies**.

---
## 🎯 **Business Objectives**
✅ **Estimate true price elasticity** of demand while accounting for selection bias.  
✅ **Understand customer spending patterns** by age, gender, and enrollment status.  
✅ **Optimize pricing decisions** using robust predictive models.  
✅ **Quantify revenue loss estimates** under biased and corrected models.  

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

## 🔧 **How to Run the Project**

### 1️⃣ Clone the Repository
```sh
git clone https://github.com/EvidenceM290/Pricing-Analysis-Starbucks.git
cd Pricing-Analysis-Starbucks
```

### 2️⃣ Install Required Libraries
```sh
pip install -r requirements.txt
```
---
## 📊 **Exploratory Data Analysis (EDA)**

### 📌 **Revenue Loss Comparison (Biased vs. Corrected Model)**
- **The uncorrected model underestimates revenue loss** from price hikes.  
- **The corrected model (Polynomial) predicts higher losses, showing greater price sensitivity.**

![Revenue Loss Comparison](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Revenue%20Loss%20Comparison.png)

### 📌 **Customer Spending Behavior**
- **Female customers spend 5.96 times more** than male customers.
- **Older customers increase spending by ~1.11% per year.**

![Spend by Enrollment](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Monthly%20Spend%20by%20Enrollment.png)

---
## 🏗 **Model Development**

### 📌 **Baseline Log-Log Regression Model**
- **Price Coefficient:** **-1.79** → A **1% price increase** leads to a **1.79% drop** in spending.
- **Adjusted R²:** **0.5676**
- **Significance:** **p < 2e-16 (Highly significant)**

![Baseline Model Summary](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Baseline%20Model.png)

---
### 📌 **Correcting Selection Bias (Heckman Model)**
- **Problem:** Starbucks only collects detailed data from **loyalty members** (selection bias).  
- **Solution:** **Heckman Two-Step Correction** predicts selection probability & adjusts estimates.  
- **Result:** The corrected **price elasticity increases to -2.13** (greater price sensitivity).  

![Heckman Model](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Heckman%20Correction.png)

---
### 📌 **Best Model: Polynomial Regression**
- **Highest Adjusted R²** (**0.7039**) → Most **accurate prediction of customer behavior.**  
- **Price Coefficient: -2.14** → **A 1% price increase = 2.14% decrease in spending.**  

![Polynomial Model Summary](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Polynomial%20Correction.png)

---
### 📌 **Random Forest Model (Alternative Approach)**
- **Predicts enrollment likelihood more accurately** than linear models.  
- **However, results show higher variance compared to Polynomial Regression.**  

![Random Forest Model](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Random%20Forest%20Correction.png)

---
### 📌 **Residual Plot Comparison (Model Performance)**
- The **Polynomial Model has the best fit**, reducing bias.  
- The **Random Forest model shows higher variance**, suggesting overfitting risk.  

![Residual Plots](https://github.com/EvidenceM290/Pricing-Analysis-Starbucks/blob/main/images/Residual%20Plot%20Comparison.png)

---
## 📌 **Business Implications & Strategic Recommendations**
### 🔹 **1. Data-Driven Pricing Strategy**
✔ **Use the Polynomial Model** for **more accurate pricing decisions.**  
✔ **Adjust prices carefully**, since customers **are highly price-sensitive (-2.14 elasticity).**  

### 🔹 **2. Customer Segmentation for Targeted Marketing**
✔ **Female customers** spend significantly more. **Target promotions to increase retention.**  
✔ **Older customers** have a **higher lifetime value** – adjust loyalty rewards accordingly.  

### 🔹 **3. Revenue Optimization**
✔ **Avoid aggressive price increases** – they could drive away price-sensitive customers.  
✔ **Introduce targeted price discounts** to maximize revenue from different customer groups.  

---
## 📌 **Final Takeaways**
✅ **Correcting selection bias is critical** – the uncorrected model **underestimates price sensitivity.**  
✅ **The best model (Polynomial Regression) reveals a stronger impact of pricing on demand.**  
✅ **Starbucks should use targeted promotions** to **retain high-value customers and optimize revenue.**  

---
## 📩 **Connect With Me**
📧 **Email:** [your-email@example.com](mailto:your-email@example.com)  
🔗 **LinkedIn:** [Your LinkedIn Profile](https://linkedin.com/in/your-profile)  
🌍 **GitHub:** [EvidenceM290](https://github.com/EvidenceM290)  

---

