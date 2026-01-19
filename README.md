

# UPI Fraud Detection System: Behavioral Risk Analytics

## 1. Project Overview

This project implements an end-to-end UPI fraud detection system designed to model risk behavior rather than just binary fraud outcomes. By integrating behavioral feature engineering, classical ML, and temporal sequence modeling, the system reflects the operational complexity of real-world fintech platforms.

---

## 2. Exploratory Data Analysis (EDA)

### 2.1 Channel-Level Vulnerabilities

Web-based transactions exhibit significantly higher fraud rates (exceeding 30%) compared to mobile platforms, highlighting channel-specific attack surfaces.

<img width="545" height="433" alt="upi_3 (1)" src="https://github.com/user-attachments/assets/c84d9df9-476f-484c-a5c2-8927e7f9b4fb" />


### 2.2 Transaction Distribution Patterns

Fraudulent transactions show distinct density peaks at specific amount ranges compared to legitimate activity, providing a baseline signal for risk scoring.
<img width="724" height="470" alt="upi_1" src="https://github.com/user-attachments/assets/519978ea-c4f0-438e-a14e-b192302cc3ee" />

---

## 3. Advanced Feature Engineering

The system moves beyond raw data by deriving contextual features that capture "how" a transaction occurs:

* 
**Location Entropy**: Measures mobility randomness; fraud often exhibits geographic unpredictability.


* 
**Merchant Fraud Rate**: Historical risk associated with the receiving entity.


* 
**User Amount Velocity**: Detecting bursts in transaction volume over short windows.



---

## 4. Modeling & Explainability

### 4.1 Global Fraud Drivers

Feature importance analysis reveals that behavioral indicators—such as merchant risk and transaction type—are stronger predictors of fraud than raw transaction amounts.

<img width="775" height="470" alt="upi_5" src="https://github.com/user-attachments/assets/2ee51ddc-e5e7-47b9-a15e-ad7e72d9abab" />


### 4.2 Network Risk Analysis

Beyond individual transactions, the system utilizes graph-based insights to identify interconnected fraud clusters and high-risk merchant communities.

<img width="1019" height="842" alt="upi_14" src="https://github.com/user-attachments/assets/26c67736-a157-4864-9bdc-350d59df1fe2" />


---

## 5. Business-Driven Evaluation

### 5.1 Threshold Optimization

Fraud thresholds are not static. I utilized a cost-sensitive framework to minimize the **Total Business Cost**, balancing the high cost of missed fraud against the friction of false alerts for legitimate users.

<img width="700" height="470" alt="upi_17" src="https://github.com/user-attachments/assets/f890f0e9-6920-4ac4-bd02-000ecfce286d" />

### 5.2 Performance Validation

The model's performance is validated through a confusion matrix, ensuring high recall for fraudulent events while maintaining acceptable precision for operational scalability.

<img width="452" height="393" alt="upi_16" src="https://github.com/user-attachments/assets/8dd5b190-ad0d-48eb-9a35-1ef5859b5971" />


---

## 6. Temporal Risk Escalation

### 6.1 User-Level Risk Evolution

The system tracks risk as a continuous variable. This visual demonstrates how user risk scores accumulate over time, allowing for proactive intervention before a confirmed fraud event occurs.

<img width="691" height="470" alt="upi_15" src="https://github.com/user-attachments/assets/4404ab04-c0ee-4dc5-a46a-54c84b019438" />


### 6.2 Actionable Decisioning

Final model outputs are bucketed into actionable risk levels to separate legitimate transactions from potential fraud.

<img width="691" height="470" alt="upi_15" src="https://github.com/user-attachments/assets/0da995ae-7566-41dd-9ace-61b34746b9ca" />


---

## 7. Tech Stack

* 
**Core**: Python, Pandas, Scikit-learn 


* 
**Deep Learning**: TensorFlow/Keras (Temporal CNN) 


* 
**Visualization**: Matplotlib, Seaborn 


* 
**Environment**: Google Colab
