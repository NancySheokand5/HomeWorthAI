# 🏠 HomeWorthAI

A machine learning project that predicts house prices using **Linear Regression**, based on square footage, bedrooms, bathrooms, house age, and location score.

Built with **Python**, **pandas**, **Matplotlib**, and **scikit-learn**.

## Overview

HomeWorthAI walks through a complete, beginner-friendly ML pipeline:

1. Load and explore housing data
2. Train a Linear Regression model
3. Evaluate the model with standard regression metrics
4. Interpret the model's coefficients
5. Predict the price of a new house from user input
6. Visualize the data and the model's performance

## Repository Contents

| File | Description |
|------|-------------|
| `task1.ipynb` | Jupyter notebook containing the full data pipeline: loading, training, evaluation, and visualization |
| `housing_price_dataset (1).csv` | Dataset used to train and test the model |
| `home worthai frontend.html` | Simple HTML frontend for entering house details and viewing predictions |
| `Screenshot 2026-09-16 093402.png` | Screenshot of the project/frontend in action |

## Dataset

The dataset contains **1,000 house records** with the following columns:

| Column | Description |
|--------|-------------|
| `square_footage` | Size of the house in square feet |
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `house_age_years` | Age of the house in years |
| `location_score` | A score (roughly 0–10) representing the desirability of the location |
| `price` | Sale price of the house (target variable) |

## Tech Stack

- **Python 3**
- **pandas** – data loading and manipulation
- **numpy** – numerical operations
- **matplotlib** – data visualization
- **scikit-learn** – model training and evaluation

## How It Works

### 1. Data Loading & Exploration
Loads the CSV file and prints a summary: first rows, column info, descriptive statistics, and a check for missing values.

### 2. Model Training
Features (`square_footage`, `bedrooms`, `bathrooms`, `house_age_years`, `location_score`) are split into training (80%) and testing (20%) sets. A `LinearRegression` model is trained on the training set.

### 3. Model Evaluation
The model is evaluated on the test set using:

- **MAE** (Mean Absolute Error) – average size of prediction error, in dollars
- **MSE** (Mean Squared Error) – average squared error, penalizes large mistakes more
- **RMSE** (Root Mean Squared Error) – same units as price, easier to interpret than MSE
- **R² Score** – how much of the price variation the model explains (closer to 1 is better)

### 4. Coefficient Interpretation
The model's learned coefficients are printed, showing how much the predicted price changes for a one-unit increase in each feature (e.g., how much price increases per extra square foot).

### 5. Predicting a New House
The user is prompted to enter square footage, bedrooms, bathrooms, house age, and location score. The model predicts and displays the estimated price.

### 6. Visualizations
Five plots are produced:

- **Square Footage vs Price** – actual vs. predicted prices
- **Distribution of House Prices** – histogram of all prices in the dataset
- **Distribution of Bedrooms** – bar chart of bedroom counts
- **Bathrooms vs Price** – scatter plot showing the relationship
- **Residual Plot** – shows prediction errors (actual − predicted) to check if the model is making balanced, unbiased predictions

## Results

On the test set, the model achieved:

- **R² ≈ 0.85–0.86** (explains ~85–86% of price variation)
- **MAE ≈ $29,000**
- **RMSE ≈ $36,000**

These are solid results for a simple linear model on this dataset.

## Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook (or JupyterLab / VS Code with Jupyter extension)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/NancySheokand5/HomeWorthAI.git
   cd HomeWorthAI
   ```

2. Install the required libraries:
   ```bash
   pip install pandas numpy matplotlib scikit-learn jupyter
   ```

### Running the Notebook

1. Launch Jupyter:
   ```bash
   jupyter notebook task1.ipynb
   ```
2. Update the file path in the notebook to point to your local copy of the dataset:
   ```python
   data = pd.read_csv(r"housing_price_dataset (1).csv")
   ```
3. Run all cells. When prompted, enter the square footage, bedrooms, bathrooms, house age, and location score for the house you want a price prediction for.

### Using the Frontend

Open `home worthai frontend.html` in your browser to try the simple interface for entering house details.

## What I Learned

- How to build a full regression pipeline: load → split → train → evaluate → predict → visualize
- The difference between MAE, MSE, RMSE, and R², and when each one is useful
- How to interpret linear regression coefficients
- Why matching feature names between training and prediction data matters (avoiding scikit-learn warnings)
- How to use a residual plot to visually check if a model's errors are random or patterned

## Possible Future Improvements

- Compare Linear Regression against other models (e.g., Random Forest, Gradient Boosting)
- Add cross-validation for a more reliable performance estimate
- Try feature engineering (e.g., price per square foot, bedroom-to-bathroom ratio)
- Connect the HTML frontend to a live backend (e.g., Flask/FastAPI) for real-time predictions
- Deploy as a web app (e.g., with Streamlit)

## Author

**Nancy Sheokand** — [@NancySheokand5](https://github.com/NancySheokand5)

Beginner ML project — first hands-on regression project using scikit-learn.

## License

This project is currently unlicensed. Consider adding a license (e.g., MIT) if you'd like others to reuse this code.
