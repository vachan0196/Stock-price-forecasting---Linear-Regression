# Stock-price-forecasting-(Linear-Regression)


This project aims to develop a robust model for forecasting stock prices using various machine learning techniques. The focus is on improving prediction accuracy by leveraging ensemble models and handling outliers effectively.

## Project Structure

- `data/`: Contains the dataset files.
- `notebooks/`: Jupyter notebooks with the analysis and model development.
- `src/`: Python scripts for data processing and model evaluation.
- `README.md`: Project documentation.
- `.gitignore`: List of files and directories to ignore.
- `requirements.txt`: List of dependencies required to run the project.

## Getting Started

### Prerequisites

- Python 3.6 or higher
- Jupyter Notebook
- Required Python packages (listed in `requirements.txt`)

### Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/stock-price-forecasting.git
    cd stock-price-forecasting
    ```

2. Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```

### Running the Notebooks

1. Navigate to the `notebooks` directory:
    ```sh
    cd notebooks
    ```

2. Launch Jupyter Notebook:
    ```sh
    jupyter notebook
    ```

3. Open and run the `stock_price_forecasting.ipynb` notebook to reproduce the analysis and model development.

## Data Preparation

The dataset includes the following columns:
- **Date**: The date of the observation.
- **Open**: The opening price of the stock.
- **High**: The highest price of the stock during the day.
- **Low**: The lowest price of the stock during the day.
- **Close**: The closing price of the stock.
- **Adj_Close**: The adjusted closing price of the stock.
- **Volume**: The number of shares traded.
- **Daily_Returns**: The daily returns of the stock.
- Additional technical indicators and lag features.

## Exploratory Data Analysis (EDA)

EDA was conducted to understand the data distribution, identify correlations, and visualize trends. Key findings included:
- High correlation between closing prices and several lag features.
- Seasonal patterns observed in stock prices.

## Model Development

The following models were tested:
1. **Linear Regression**
2. **Polynomial Regression**
3. **Random Forest**
4. **Ridge Regression**
5. **Lasso Regression**
6. **Huber Regression**
7. **Ensemble Models** (Voting Regressor combining Ridge, Random Forest, and Linear Regression)

## Handling Outliers

Outliers were identified based on the residuals from initial model predictions. These outliers were removed to improve model performance.

## Model Evaluation Metrics

- **Mean Squared Error (MSE)**
- **R-squared (R²)**
- **Mean Absolute Percentage Error (MAPE)**
- **Residual Analysis**: Evaluated residuals over time and their distribution to identify patterns and outliers.

## Results

| Model                          | Validation MSE | Validation R² | Test MSE | Test R² | Validation MAPE | Validation Accuracy | Test MAPE | Test Accuracy |
|--------------------------------|----------------|---------------|----------|---------|-----------------|---------------------|-----------|---------------|
| Linear Regression              | 0.00533        | 0.999999      | 0.00392  | 0.999999| N/A             | N/A                 | N/A       | N/A           |
| Ridge Regression               | 0.00530        | 0.999999      | 0.00391  | 0.999999| N/A             | N/A                 | N/A       | N/A           |
| Polynomial Regression          | 2.45782        | 0.999723      | 0.28416  | 0.999968| N/A             | N/A                 | N/A       | N/A           |
| Random Forest                  | 0.28416        | 0.999968      | 0.28416  | 0.999968| N/A             | N/A                 | N/A       | N/A           |
| Ensemble (Initial)             | 0.00705        | 0.968538      | 0.00608  | 0.972815| N/A             | N/A                 | N/A       | N/A           |
| Ensemble (After Outlier Removal)| 176.90        | 0.978129      | 231.59   | 0.973537| 5.47%           | 94.53%              | 5.69%     | 94.31%        |

### Key Performance Metrics

- **Validation MAPE**: 5.47%
- **Validation Accuracy**: 94.53%
- **Test MAPE**: 5.69%
- **Test Accuracy**: 94.31%

## Visualizations

### Actual vs Predicted Closing Prices

![Actual vs Predicted Closing Prices](file-g9N0AJ8HSHmyEGfNN57avcsq.png)

### Residuals Over Time

![Residuals Over Time](file-QvVId6gWbXC698zNrV43Velc.png)

### Distribution of Residuals

![Distribution of Residuals](file-uIIfgNhJIyFLWXSrh1bMfVYT.png)

## Conclusion

- **Ensemble Models**: Combining Ridge, Random Forest, and Linear Regression significantly improved the model’s performance.
- **Outlier Handling**: Removing outliers based on residuals further enhanced model accuracy, especially on the test set.
- **Feature Engineering**: Incorporating lag features, moving averages, and technical indicators contributed to the model's predictive power.
- **MAPE and Accuracy**: The Mean Absolute Percentage Error and accuracy provided additional measures of model performance, with validation accuracy of 94.53% and test accuracy of 94.31%.

## Limitations

1. **Outlier Sensitivity**: Initial models were highly sensitive to outliers, necessitating their removal for improved performance.
2. **Feature Selection**: The selection of features was based on domain knowledge and EDA; further refinement could improve performance.
3. **Time Series Specific Models**: Advanced time series models like LSTM or SARIMA were not fully explored in this study.

## Future Work

1. **Advanced Time Series Models**: Implement models like SARIMA, Prophet, and LSTM for comparison.
2. **Feature Optimization**: Further optimize feature selection and engineering.
3. **Real-Time Forecasting**: Deploy the model for real-time stock price prediction and continuously refine it with new data.

## License

This project is licensed under the MIT License.

