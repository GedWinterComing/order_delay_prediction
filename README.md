# 🚚 Order Delay Classifier: Machine Learning for Logistics

## 📌 Project Overview
This project is an interactive Machine Learning WebApp built with Python and Streamlit. Its primary goal is to predict potential shipping delays before they occur, providing a risk-assessment tool for supply chain and operational managers. 

The project was developed during the **Academy Data Scientist (Adecco @ Crif, Nov-Dec 2025)** by Gabriele Coppini, Gaia Guerra, Simone Morelli, and Umberto Schiavone.

## 💼 Business Problem
In modern companies, delivery management is increasingly risk-averse. Anticipating a potential delay is an economically and strategically prudent choice to prevent:
* Contractual penalties and refunds
* Extra transportation and operational costs
* Loss of customer trust and reputational damage

## 📊 Data & Feature Engineering
The dataset was sourced from the *Kaggle Datathon 2022 UPC - Accenture*, comprising over 114,000 records.
https://www.kaggle.com/competitions/prueba-competencia/data

To improve model performance, extensive feature engineering was applied:
* **Categorical Feature Fusion:** Combined features to capture specific logistical bottlenecks (e.g., Route + Courier, Courier + Customs procedures).
* **Numerical Transformations:** Transformed shipment weights into categorical risk classes using quartiles and calculated Z-scores for weights and units based on specific routes.

## 🧠 Modeling Strategy
Several models were evaluated to beat the Logistic Regression baseline, including Random Forest, HistGradientBoosting, LightGBM, and Neural Networks. 

**Final Choice: CatBoost**
* **Evaluation Metric:** The model was optimized for **Recall** on the "late order" class. From a business perspective, it is preferable to flag more at-risk orders (accepting some false positives) rather than missing a critical delay.
* **Results:** CatBoost significantly outperformed the baseline, achieving a **Recall of 83%** (vs. 60% of Logistic Regression) and an **F1-Score of 0.545** (vs. 0.442).

## 🖥️ The WebApp
The final product is a Streamlit dashboard allowing users to input new shipment details (Origin Port, Logistic Hub, Customer City, Courier, Weight, etc.) and instantly receive a prediction. 
The app outputs the probability of delay and categorizes the risk level, enabling proactive operational interventions.
https://orderdelayprediction-n4gpqgztxjmw8bycb4cyq4.streamlit.app/

## 🛠️ Tech Stack
* **Language:** Python.
* **Machine Learning:** CatBoost, Scikit-learn, Pandas, NumPy.
* **Deployment & UI:** Streamlit.
