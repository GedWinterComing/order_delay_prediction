# 🚚 Order Delay Classifier: Machine Learning for Logistics

## 📌 Project Overview
This project is an interactive Machine Learning WebApp built with Python and Streamlit. Its primary goal is to predict potential shipping delays before they occur, providing a risk-assessment tool for supply chain and operational managers. 

[cite_start]The project was developed during the **Data Scientist Academy (Adecco @ Crif, Nov-Dec 2025)** by Gabriele Coppini, Gaia Guerra, Simone Morelli, and Umberto Schiavone[cite: 61, 64, 65].

## 💼 Business Problem
[cite_start]In modern companies, delivery management is increasingly risk-averse[cite: 67]. [cite_start]Anticipating a potential delay is an economically and strategically prudent choice to prevent[cite: 68, 70]:
* [cite_start]Contractual penalties and refunds [cite: 71]
* [cite_start]Extra transportation and operational costs [cite: 72, 73]
* [cite_start]Loss of customer trust and reputational damage [cite: 74, 75, 76, 77]

## 📊 Data & Feature Engineering
[cite_start]The dataset was sourced from the *Kaggle Datathon 2022 UPC - Accenture*, comprising over 114,000 records[cite: 86, 94]. 

[cite_start]To improve model performance, extensive feature engineering was applied[cite: 103, 134]:
* [cite_start]**Categorical Feature Fusion:** Combined features to capture specific logistical bottlenecks (e.g., Route + Courier, Courier + Customs procedures)[cite: 167, 170].
* [cite_start]**Numerical Transformations:** Transformed shipment weights into categorical risk classes using quartiles and calculated Z-scores for weights and units based on specific routes[cite: 129, 188].

## 🧠 Modeling Strategy
[cite_start]Several models were evaluated to beat the Logistic Regression baseline, including Random Forest, HistGradientBoosting, LightGBM, and Neural Networks[cite: 197, 212, 214, 219, 220]. 

[cite_start]**Final Choice: CatBoost** [cite: 213, 228]
* [cite_start]**Evaluation Metric:** The model was optimized for **Recall** on the "late order" class[cite: 81]. [cite_start]From a business perspective, it is preferable to flag more at-risk orders (accepting some false positives) rather than missing a critical delay[cite: 79, 80, 82, 259].
* [cite_start]**Results:** CatBoost significantly outperformed the baseline, achieving a **Recall of 83%** (vs. 60% of Logistic Regression) and an **F1-Score of 0.545** (vs. 0.442)[cite: 236, 237, 240, 244].

## 🖥️ The WebApp
[cite_start]The final product is a Streamlit dashboard allowing users to input new shipment details (Origin Port, Logistic Hub, Customer City, Courier, Weight, etc.) and instantly receive a prediction[cite: 297, 303, 305, 307, 309, 311, 324, 326]. 
[cite_start]The app outputs the probability of delay and categorizes the risk level, enabling proactive operational interventions[cite: 303, 325, 387].

## 🛠️ Tech Stack
* [cite_start]**Language:** Python [cite: 54]
* [cite_start]**Machine Learning:** CatBoost, Scikit-learn, Pandas, NumPy [cite: 50, 54]
* [cite_start]**Deployment & UI:** Streamlit [cite: 297]
