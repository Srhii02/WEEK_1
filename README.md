Project: Carbon Emission Prediction
# CO₂ Emissions Data Cleaning

This project involves cleaning and preparing country-specific CO₂ emissions and related data for further analysis and modeling.

## 📁 Dataset Description

The original dataset contains:
- Country information
- Various indicators over multiple years (1990–2011)
- Wide-format year columns (e.g., '1990', '1991', ...)

## 🧹 Data Cleaning Steps

1. **Loaded the raw data** into a Pandas DataFrame.
2. **Transformed the dataset from wide to long format** using `pd.melt()`, converting year columns into a single 'year' column.
3. **Checked and counted missing values**:
   - By year
   - By country
   - By column
4. **Filtered**:
   - Years between 1991 and 2008 (to reduce missing values)
   - Countries with **no missing values** (or optionally minimal missing values)
5. **Exported** the cleaned dataset to:
   - `cleaned_data.csv`

## 🗃️ Output

- `cleaned_data.csv`: Long-format cleaned dataset ready for analysis or modeling.
- This project implements a univariate time series forecasting model using an LSTM neural network in Keras.
The model uses a sliding window approach to predict future values based on past observations.

Features:
---------
- LSTM-based model for sequence learning
- Sliding window data preparation
- Time series forecasting with visualization
- Simple, easy-to-understand implementation

Requirements:
-------------
Install the required libraries using:

    pip install pandas numpy matplotlib tensorflow

Model Architecture:
-------------------
Input shape: (window_size, 1)
→ LSTM(64 units)
→ Dense(1 unit)

Steps:
------
1. Prepare the dataset using a sliding window function:

    def create_dataset(X, y, time_step=1):
        ...

2. Reshape the input:

    X = X.reshape((X.shape[0], X.shape[1], 1))

3. Build and compile the model:

    model = Sequential([
        Input(shape=(window_size, 1)),
        LSTM(64),
        Dense(1)
    ])
    model.compile(optimizer='adam', loss='mse')

4. Train the model:

    model.fit(X, y, epochs=100, batch_size=4)

5. Predict and visualize:

    predictions = model.predict(X)
    plt.plot(y, label='Actual')
    plt.plot(predictions, label='Predicted')
    plt.legend()

Output:
-------
The script plots actual vs. predicted values for the training set.
Missing values and non-numeric entries were handled and cleaned.
Multiple machine learning models were trained and evaluated, with Gradient Boosting achieving R² > 95%.
Feature importance was visualized to interpret key emission drivers.
A custom PowerPoint presentation was auto-generated using the provided template.







