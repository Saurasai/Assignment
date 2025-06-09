# 🏙️ Dubai Property Price Prediction & Valuation Tool

This project builds a machine learning-based solution to predict property prices in Dubai and classify listings as **underpriced**, **fairly priced**, or **overpriced**. The model is integrated into a user-friendly web application for real-time price valuation.

## 🚀 Features

- Predicts property prices using key features like size, rooms, and location.
- Classifies listings based on valuation logic.
- Warns about unrealistic prices using price/sqft bounds.
- Flask web app for live predictions with a simple UI.
- Supports form and JSON input for flexibility.

---

## 📊 Dataset & Features

**Key Input Features:**
- Size (sqft)
- Bedrooms
- Bathrooms
- Neighbourhood
- Building

**Target Variable:**
- Price (AED)

**Engineered Features:**
- `price_per_sqft` = price / size
- `total_rooms` = bedrooms + bathrooms
- Slimmed-down categories for buildings and neighbourhoods

---

## 🧹 Data Preprocessing

- Missing values handled via median/imputation.
- Rare categories grouped into "Other".
- Selected numerical & categorical features for training.
- Saved pipeline with preprocessor and trained model.

---

## 🧠 Model

- **Model Used**: Random Forest Regressor
- **Train-Test Split**: 80% - 20%
- **Evaluation Metrics**:
  - R² Score
  - Mean Absolute Error (MAE)

---

## 🧮 Valuation Logic

Based on comparison of actual vs predicted prices:
- **Underpriced**: Actual < Predicted - 10%
- **Fairly Priced**: Within ±10% range
- **Overpriced**: Actual > Predicted + 10%

Includes sanity checks using price per sqft thresholds.

---

## 🌐 Web App

Built using **Flask** and deployed with **Gunicorn**.

### Features:
- Simple input form for users.
- Displays:
  - Predicted Price
  - Valuation Result
  - Validation Warnings (if any)
- Supports both form-based UI and JSON API.

---

## 🛠️ Setup Instructions

```bash
# Clone the repository
git clone https://github.com/your-username/property-price-prediction.git
cd property-price-prediction

# Install dependencies
pip install -r requirements.txt

# Run the app locally
python app.py

 
