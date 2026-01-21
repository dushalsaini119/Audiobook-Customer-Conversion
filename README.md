# Audiobook Customer Conversion Prediction

## 📌 Problem Overview
The objective of this project is to predict whether a customer will purchase an audiobook again.

Customer behavior was tracked for **2 years**, and then for the next **6 months** it was recorded whether the customer bought an audiobook again or not.

This is a **binary classification problem**:
- **1** → Customer bought again (converted)
- **0** → Customer did not buy again

---

## 📊 Dataset Information
- Original dataset size: **14,083 customers**
- Final dataset size after balancing: **4,474 customers**
- Total columns: **12**
- Features used for modeling: **10**
- Target variable: Customer conversion (0 or 1)

Each row represents one customer and their historical audiobook behavior.

---

## 🧾 Dataset Columns Description

| Column Name | Description |
|------------|------------|
| `ID` | Unique identifier for each customer |
| `Book_length(mins)_avg` | Average length (in minutes) of audiobooks purchased |
| `Book_length(mins)_overall` | Total audiobook length (in minutes) purchased by the customer |
| `Price_avg` | Average price of audiobooks purchased |
| `Price_overall` | Total amount spent on audiobooks |
| `Review` | Whether the customer left a review (Yes/No) |
| `Review 10/10` | Review rating out of 10 (missing values filled with average rating **8.91**) |
| `Completion` | Percentage of audiobook completed by the customer |
| `Minutes_listened` | Total minutes spent listening to audiobooks |
| `Support_request` | Number of times the customer contacted support |
| `Last_visited − Purchase_date` | Engagement duration (days between last visit and purchase date) |
| `Target` | **1** if customer bought again in next 6 months, **0** otherwise |

---

## ⚠️ Class Imbalance & Data Balancing
The original dataset was **highly imbalanced**, with far more non-converted customers than converted ones.

To build an **honest and unbiased model**:
- All converted customers were retained
- Excess non-converted customers were removed

📉 After balancing, the dataset was reduced to **4,474 samples**.  
This step prevents the model from learning a bias toward the majority class and improves real-world prediction reliability.

---

## 🎯 Business Objective
The goal is to help the business:
- Identify customers who are likely to convert
- Focus marketing and retention efforts on engaged users
- Reduce spending on customers unlikely to purchase again

---

## 🧠 Approach Used
1. Handled class imbalance through data balancing  
2. Standardized features for better neural network performance  
3. Split data into **training, validation, and test sets**  
4. Built a **neural network using TensorFlow/Keras**  
5. Used **early stopping** to avoid overfitting  

---

## 🧪 Model Testing & Performance
- The model was evaluated on a **test dataset that was never seen during training**
- Achieved approximately **83% accuracy** on real-world, preprocessed test data

### 🔍 Interpretation
> If we are given audiobook activity data of **10 customers**, the model can correctly predict the future purchase behavior of **about 8 customers**.

---

## 🛠 Tech Stack
- Python  
- NumPy, Pandas  
- Scikit-learn  
- TensorFlow / Keras  

---

## 📁 Project Structure
- `notebooks/` → End-to-end Jupyter notebook (preprocessing, training, testing)
- `models/` → Saved trained neural network model
- `data/` → Dataset
- `README.md` → Project overview
