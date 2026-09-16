# AdOptima - Influencer Campaign Sales Prediction

**AdOptima** is a Machine Learning project designed to predict the expected product sales of influencer marketing campaigns prior to execution[cite: 3]. By leveraging campaign variables such as social media platform, influencer tier, and campaign type, AdOptima enables companies to optimize marketing decisions and minimize financial risk[cite: 3].

---

## 👥 Team Members
* **Sadeen**[cite: 3]
* **Maemonah**[cite: 3]
* **Khadejah**[cite: 3]
* **Layan**[cite: 3]

---

## 📌 Project Overview
In modern marketing, choosing the right social media platform and campaign structure is critical to achieving a high ROI[cite: 3]. AdOptima builds a predictive regression model that estimates `product_sales` based on key campaign parameters[cite: 3].

* **Goal:** Predict expected sales for influencer campaigns[cite: 3].
* **Task Type:** Supervised Machine Learning (Regression)[cite: 3].
* **Target Variable:** `product_sales`[cite: 3].

---

## 📊 Dataset & Exploratory Data Analysis (EDA)

The project utilizes a dataset containing 400 campaign records with both numeric and categorical variables[cite: 3]:

### **Dataset Features:**
* `campaign_id`: Unique identifier for each campaign[cite: 3].
* `platform`: Social media platform used (`Instagram`, `YouTube`)[cite: 3].
* `influencer_category`: Influencer tier (`Micro`, `Mid-tier`, `Macro`, `Mega`)[cite: 3].
* `campaign_type`: Format of the campaign (`Product Launch`, `Sponsored Post`, `Giveaway`, `Brand Awareness`)[cite: 3].
* `start_date` & `end_date`: Start and end dates of the campaign[cite: 3].
* `engagements`: Total engagement interactions[cite: 3].
* `estimated_reach`: Estimated audience reach[cite: 3].
* `campaign_duration_days`: Duration of the campaign in days[cite: 3].
* **`product_sales` (Target):** Units/volume of product sold[cite: 3].

---

## 🛠️ Data Preprocessing & Cleaning

1. **Handling Missing Values:**
   * Calculated `campaign_duration_days` from `start_date` and `end_date` where missing[cite: 3].
   * Handled missing target values and missing categorical fields appropriately[cite: 3].
2. **Data Sanitation:**
   * Corrected noisy and negative values in numeric variables (e.g., taking absolute values for `estimated_reach` / `engagements`)[cite: 3].
3. **Target Transformation:**
   * Applied **Log Transformation** to `product_sales` on the training dataset to reduce target distribution skewness[cite: 3].

---

## ⚙️ Model Training & Validation Strategy

* **Train / Test Split:** 80% Training Data, 20% Testing Data (`random_state=42`)[cite: 3].
* **Cross-Validation:** 10-Fold Stratified Cross-Validation on training data to prevent overfitting and data leakage[cite: 3].
* **Model Algorithm:** **CatBoost Regressor**[cite: 3].

### **CatBoost Model Hyperparameters:**
| Parameter | Value | Description |
| :--- | :--- | :--- |
| `iterations` | 1800 | Number of boosting trees[cite: 3] |
| `learning_rate` | 0.02 | Small step size for stable learning[cite: 3] |
| `depth` | 4 | Controls tree complexity[cite: 3] |
| `l2_leaf_reg` | 8 | L2 regularization to prevent overfitting[cite: 3] |
| `loss_function` | `RMSE` | Regression loss function[cite: 3] |
| `bootstrap_type` | `Bernoulli` | Random row sampling for trees[cite: 3] |
| `subsample` | 0.85 | Uses 85% of samples per tree[cite: 3] |
| `random_strength`| 1.0 | Adds randomness to split selection[cite: 3] |
| `min_data_in_leaf`| 5 | Minimum samples per leaf[cite: 3] |
| `border_count` | 128 | Number of bins for numerical features[cite: 3] |
| `random_seed` | 42 | Ensures reproducible results[cite: 3] |

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
