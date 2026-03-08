# Air Quality Index (AQI) Prediction Using CNN-LSTM

This project predicts the Air Quality Index (AQI) using a **hybrid CNN-LSTM model**. The model takes historical pollution data for a city and forecasts the AQI for the next day.

---

## Dataset

- Source: [India's Air Quality Dataset on Kaggle](https://www.kaggle.com/datasets/harshar1210/indias-air-quality)  
- The notebook focuses on **Delhi**, but it can be adapted for other cities.  
- Only the file `city_day.csv` is required from the dataset.

---

## Features Used

The model uses six pollutant features as input:

- PM2.5  
- PM10  
- NO2  
- CO  
- SO2  
- O3  

The target is the daily **AQI**.

---

## How to Run

1. Download `city_day.csv` from the Kaggle link above.  
2. Place the CSV in the same folder as the notebook, or update the path in the code.  
3. Install required Python packages:
    ```bash
    pip install pandas numpy matplotlib scikit-learn tensorflow
    ```
4. Open `cnn_lstm_aqi_prediction.ipynb` in Jupyter Notebook and run all cells.

---

## Model Details

- **CNN Layer**: Detects local patterns in pollution data over consecutive days.  
- **MaxPooling1D**: Reduces sequence length and retains strongest features.  
- **LSTM Layer**: Captures long-term dependencies in the time series.  
- **Dense Layer**: Outputs the predicted AQI.  
- **Dropout**: Prevents overfitting.  
- **Activation**: ReLU for hidden layers, linear for output.  
- **Optimizer**: Adam  
- **Loss**: Mean Squared Error (MSE)

- **Sequence length used**: 25 (past 25 days of data to predict next day AQI)

---

## Results

- **RMSE**: ~40 on test data (Delhi)  
- Graphs of **Predicted vs Actual AQI** are included in the notebook.  

---

## Notes

- The sequence length is important: too short misses trends, too long adds noise.  
- This notebook can be extended to include more features like temperature, humidity, or wind speed for potentially better predictions.

---
