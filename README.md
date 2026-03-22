# 🛡️ IoT Intrusion Detection System (99.7% Accuracy)

An end-to-end Machine Learning pipeline designed to identify and classify malicious network traffic in IoT environments. This project focuses on high-precision detection of **DDoS, DoS, and Reconnaissance** attacks using the **Bot-IoT dataset**.

---

## 👥 The Incredible Team
This project was a collaborative effort by an **incredible team** under the supervision of **Eng. Antonios Malak**.
* **Team Members:** [Toka Mustafa], [Gellan Romany], [Rewan Wael] ,[Reham Haroun Mousa]

---

## 🚀 Project Highlights

### 1. Eliminating Data Leakage
To ensure real-world reliability, we meticulously removed "cheating" features that often lead to over-optimistic results:
* Dropped direct indicators like `attack` and `subcategory`.
* Removed sequence identifiers and timestamps (`pkSeqID`, `stime`, `ltime`) to prevent the model from memorizing attack order.
* Stripped IP/MAC addresses to ensure the model generalizes to any network.

### 2. Advanced Feature Engineering
* **Behavioral Port Grouping:** Grouped 65k+ ports into **Well-Known**, **Registered**, and **Dynamic** categories to capture scanning patterns.
* **Taming Skewness:** Applied **Log Transformation** and **Yeo-Johnson PowerTransformer** to normalize highly skewed network flow rates.
* **Outlier Resilience:** Utilized **RobustScaler** to maintain stability during extreme traffic spikes.

---

## 📊 Performance & Insights

We compared two powerhouse algorithms, both achieving exceptional results:

| Model | Test Accuracy | Key Driver (Feature Importance) |
| :--- | :---: | :--- |
| **XGBoost** | **99.71%** | Network Flags (`flgs`) |
| **Random Forest** | **99.68%** | Source Rate (`srate`) |

### Key Takeaway:
The models revealed that the **type of connection attempt (Flags)** and the **traffic volume (Rate)** are the most critical signatures of botnet activity.

---

## 🛠️ Tech Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-Learn, XGBoost, Matplotlib, Seaborn
* **Environment:** Kaggle / Jupyter Notebook

---

## 📂 How to Use
1. Clone the repository.
2. Ensure you have the dependencies installed: `pip install pandas xgboost scikit-learn`.
3. Run the notebook/script to see the preprocessing and model evaluation.

---

## 🔗 Project Links
* **Kaggle Notebook:** [https://www.kaggle.com/code/tokamustafa/network-attacks]
