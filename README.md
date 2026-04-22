# 📉 Customer Churn Prediction

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/XGBoost-Gradient%20Boosting-red?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" />
</p>

<p align="center">
  A comprehensive machine learning project that predicts customer churn in the telecom industry using <strong>Logistic Regression</strong>, <strong>Random Forest</strong>, and <strong>XGBoost</strong>, combined with <strong>K-Means clustering</strong> for customer segmentation.
</p>

---

## 📚 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Workflow](#-workflow)
- [Models & Results](#-models--results)
- [Customer Segmentation](#-customer-segmentation)
- [Installation](#-installation)
- [Usage](#-usage)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🔍 Overview

Customer churn — when customers stop using a service — is a critical challenge for telecom companies. This project uses supervised machine learning to **predict whether a customer will churn**, and unsupervised learning to **segment customers** into meaningful groups, enabling targeted retention strategies.

### ✅ Key Objectives:
- Predict churn with high accuracy using multiple ML classifiers
- Compare model performance using Accuracy, ROC-AUC, and Classification Reports
- Segment customers using K-Means Clustering and visualize with PCA
- Engineer meaningful features from raw telecom data

---

## 📊 Dataset

| Dataset | Description | Records |
|---|---|---|
| **WA_Fn-UseC_-Telco-Customer-Churn.csv** | IBM Watson Telco Customer Churn Dataset | ~7,000 |
| **customer_churn_dataset-testing-master.csv** | Extended testing dataset | ~50,000 |

### 🔑 Key Features:
- `tenure` — Number of months the customer has stayed
- `MonthlyCharges` — Monthly subscription charge
- `TotalCharges` — Total amount charged
- `Contract` — Type of contract (Month-to-month, One year, Two year)
- `InternetService` — Type of internet service
- `PaymentMethod` — Payment method used
- `Churn` — Target variable (Yes/No → 1/0)

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| **Language** | Python 3.8+ |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn |
| **Machine Learning** | Scikit-Learn |
| **Gradient Boosting** | XGBoost |
| **Dimensionality Reduction** | PCA |
| **Clustering** | K-Means |
| **Environment** | Jupyter Notebook |

---

## 📁 Project Structure

```
Customer_Churn_Prediction/
│
├── 📓 Customer_Churn_Prediction.ipynb        # Main Jupyter Notebook
├── 📄 WA_Fn-UseC_-Telco-Customer-Churn.csv   # Primary dataset (IBM Telco)
├── 📄 customer_churn_dataset-testing-master.csv  # Extended test dataset
└── 📘 README.md                               # Project documentation
```

---

## 🔄 Workflow

```
Raw Data → EDA → Feature Engineering → Preprocessing → Model Training → Evaluation → Clustering → Visualization
```

### Step-by-Step Pipeline:

1. **Data Loading** — Load the IBM Telco dataset using Pandas
2. **Exploratory Data Analysis (EDA)** — Visualize churn distribution and feature relationships
3. **Preprocessing**
   - Drop irrelevant columns (`customerID`)
   - Convert `TotalCharges` to numeric
   - Encode target variable `Churn` (Yes → 1, No → 0)
   - One-hot encode categorical variables
4. **Feature Engineering**
   - `charges_per_month` = TotalCharges / (tenure + 1)
   - `is_long_term` = 1 if tenure > 24 months, else 0
5. **Train/Test Split** — 80% training, 20% testing (`random_state=42`)
6. **Imputation** — Median imputation for missing values
7. **Scaling** — StandardScaler for feature normalization
8. **Model Training** — 3 classifiers trained and compared
9. **Evaluation** — Accuracy, ROC-AUC, and full classification report
10. **Clustering** — K-Means with 4 clusters + PCA visualization

---

## 🤖 Models & Results

### Models Trained:

| Model | Description |
|---|---|
| **Logistic Regression** | Baseline linear classifier, `max_iter=1000` |
| **Random Forest** | Ensemble of 200 decision trees |
| **XGBoost** | Gradient boosting with `logloss` eval metric |

### Evaluation Metrics Used:
- **Accuracy Score**
- **ROC-AUC Score**
- **Precision, Recall, F1-Score** (via Classification Report)
- **Confusion Matrix**

> 📌 XGBoost typically achieves the **best performance** on churn classification tasks due to its ability to handle imbalanced data and capture complex feature interactions.

---

## 🗺️ Customer Segmentation

In addition to churn prediction, the project applies **unsupervised learning** to group customers:

- **Algorithm**: K-Means Clustering (`n_clusters=4`)
- **Preprocessing**: Median Imputation → StandardScaler
- **Visualization**: PCA reduces features to 2D for scatter plot visualization using Seaborn

This segmentation helps identify high-risk churn segments for targeted business interventions.

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/priyankametar123/Customer_Churn_Prediction.git
cd Customer_Churn_Prediction
```

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate
```

### 3. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter
```

---

## 🚀 Usage

### Run the Notebook

```bash
jupyter notebook Customer_Churn_Prediction.ipynb
```

Then execute cells in order from top to bottom.

### Quick Start (All cells at once)

```bash
jupyter nbconvert --to notebook --execute Customer_Churn_Prediction.ipynb --output executed_output.ipynb
```

---

## 📈 Sample Visualizations

The notebook generates the following visualizations:

| Plot | Description |
|---|---|
| **Churn Distribution** | Count plot of churned vs. non-churned customers |
| **Customer Segments** | 2D PCA scatter plot with K-Means cluster labels |

---

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Priyanka Metar**  
📧 GitHub: [@priyankametar123](https://github.com/priyankametar123)

---

<p align="center">⭐ If you found this project useful, please star the repository!</p>
