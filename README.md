# Fraud Detection System Using Machine Learning

This project builds a machine learning pipeline to detect fraudulent financial transactions based on a large dataset of over 1 million records. It involves thorough exploratory data analysis, feature engineering, data balancing, model training, and performance evaluation.

## 📊 Dataset Description

The dataset contains the following fields:
- `step`: Hour of the transaction.
- `type`: Type of transaction (e.g., CASH_OUT, PAYMENT, TRANSFER).
- `amount`: Transaction amount.
- `customer_starting_transaction`, `recipient_of_transaction`: Unique IDs.
- `bal_before_transaction`, `bal_after_transaction`: Account balances of the customer.
- `bal_of_recipient_before_transaction`, `bal_of_recipient_after_transaction`: Account balances of the recipient.
- `fraud_transaction`: Target variable (`1` if fraud, else `0`).

The dataset is **highly imbalanced**, with frauds constituting only ~0.1% of all transactions.

## 🧪 Exploratory Data Analysis

- Univariate, Bivariate, and Multivariate visualizations using seaborn and matplotlib.
- Key insights:
  - `TRANSFER` and `CASH_OUT` are the most fraud-prone transaction types.
  - Fraud transactions are rare but significant.
  - Highly imbalanced class distribution.
  
## 🔧 Feature Engineering

- One-hot encoding of categorical variables.
- Removal of high-cardinality and leak-prone features.
- Conversion of float64 and int64 columns to float32/int32 to optimize memory usage.

## ⚖️ Data Balancing

Used `RandomUnderSampler` from `imblearn` to address the class imbalance by undersampling the majority class (non-fraud).

## 🤖 Models Used

The following models were trained and evaluated:
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Random Forest

### 📈 Performance Summary

| Model               | Accuracy | Precision (Fraud) | Recall (Fraud) | F1-score (Fraud) |
|--------------------|----------|-------------------|----------------|------------------|
| Logistic Regression| 93.87%   | 78%               | 35%            | 49%              |
| KNN                | 92.48%   | 56%               | 37%            | 45%              |
| Decision Tree      | 96.70%   | 92%               | 65%            | 76%              |
| Random Forest      | 96.62%   | 90%               | 66%            | 76%              |

- **Random Forest** had the best recall and generalization ability.
- **Decision Tree** was a close second.

## ✅ Conclusion

- Fraud detection requires balancing **recall** and **precision**.
- **Random Forest** was chosen as the final model due to its better recall performance.

## 💡 Recommendations

- Implement two-factor authentication.
- Enforce password/PIN changes regularly.
- Track suspicious patterns like frequent failed login attempts.
- Improve data quality and balance for future model training.

## 📁 Project Structure

📦 Fraud_Detection_ML
┣ 📄 dataset.csv
┣ 📄 fraud_detection.py
┣ 📄 README.md
┗ 📄 requirements.txt


## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/Fraud_Detection_ML.git
   cd Fraud_Detection_ML
2. Install dependencies:

   pip install -r requirements.txt

3. Run the notebook or script to train and evaluate models:

   python fraud_detection.py
## 📄 License

This project is licensed under the [MIT License](LICENSE).
