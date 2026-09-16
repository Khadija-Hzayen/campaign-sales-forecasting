# AdOptima - Influencer Campaign Sales Prediction

**AdOptima** is a Machine Learning project designed to predict the expected product sales of influencer marketing campaigns prior to execution. By leveraging campaign variables such as social media platform, influencer tier, and campaign type, AdOptima enables companies to optimize marketing decisions and minimize financial risk.

---

## 👥 Team Members
* **Sadeen**
* **Maemonah**
* **Khadejah**
* **Layan**

---

## 📌 Project Overview
In modern marketing, choosing the right social media platform and campaign structure is critical to achieving a high ROI. AdOptima builds a predictive regression model that estimates `product_sales` based on key campaign parameters.

* **Goal:** Predict expected sales for influencer campaigns.
* **Task Type:** Supervised Machine Learning (Regression).
* **Target Variable:** `product_sales`.

---

## 📊 Dataset & Exploratory Data Analysis (EDA)

The project utilizes a dataset containing 400 campaign records with both numeric and categorical variables:

### **Dataset Features:**
* `campaign_id`: Unique identifier for each campaign.
* `platform`: Social media platform used (`Instagram`, `YouTube`).
* `influencer_category`: Influencer tier (`Micro`, `Mid-tier`, `Macro`, `Mega`).
* `campaign_type`: Format of the campaign (`Product Launch`, `Sponsored Post`, `Giveaway`, `Brand Awareness`).
* `start_date` & `end_date`: Start and end dates of the campaign.
* `engagements`: Total engagement interactions.
* `estimated_reach`: Estimated audience reach.
* `campaign_duration_days`: Duration of the campaign in days.
* **`product_sales` (Target):** Units/volume of product sold.

---

## 🛠️ Data Preprocessing & Cleaning

1. **Handling Missing Values:**
   * Calculated `campaign_duration_days` from `start_date` and `end_date` where missing.
   * Handled missing target values and missing categorical fields appropriately.
2. **Data Sanitation:**
   * Corrected noisy and negative values in numeric variables (e.g., taking absolute values for `estimated_reach` / `engagements`).
3. **Target Transformation:**
   * Applied **Log Transformation** to `product_sales` on the training dataset to reduce target distribution skewness.

---

## ⚙️ Model Training & Validation Strategy

* **Train / Test Split:** 80% Training Data, 20% Testing Data (`random_state=42`).
* **Cross-Validation:** 10-Fold Stratified Cross-Validation on training data to prevent overfitting and data leakage.
* **Model Algorithm:** **CatBoost Regressor**.

### **CatBoost Model Hyperparameters:**
| Parameter | Value | Description |
| :--- | :--- | :--- |
| `iterations` | 1800 | Number of boosting trees |
| `learning_rate` | 0.02 | Small step size for stable learning |
| `depth` | 4 | Controls tree complexity |
| `l2_leaf_reg` | 8 | L2 regularization to prevent overfitting |
| `loss_function` | `RMSE` | Regression loss function |
| `bootstrap_type` | `Bernoulli` | Random row sampling for trees |
| `subsample` | 0.85 | Uses 85% of samples per tree |
| `random_strength`| 1.0 | Adds randomness to split selection |
| `min_data_in_leaf`| 5 | Minimum samples per leaf |
| `border_count` | 128 | Number of bins for numerical features |
| `random_seed` | 42 | Ensures reproducible results |

---

## 💻 Tech Stack & Libraries
* **Language:** Python
* **Data Processing:** `pandas`, `numpy`
* **Machine Learning:** `scikit-learn`, `catboost`
* **Visualization:** `matplotlib`, `seaborn`

---

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/AdOptima.git](https://github.com/your-username/AdOptima.git)
   cd AdOptima
