#PROJECT


---

# 📈 Stock Market Prediction using Deep Learning

## 🔹 About the Project

In this project, I tried to predict stock prices using Deep Learning techniques. The idea was to understand how stock market data behaves over time and how machine learning models can learn patterns from it.

I used historical stock price data and applied GRU and LSTM models, which are specially designed for time-series data. This project helped me understand both data handling and model training in a practical way.

---


What I Used
Python
Pandas & NumPy for handling data
Matplotlib for graphs
Scikit-learn for scaling
Keras (TensorFlow) for building the model
## 🔹 Dataset Used

There are mainly two datasets used in this project:

* **prices.csv** → contains daily stock prices like open, close, date, and symbol
* **securities.csv** → contains company-related information

First, I explored the dataset to understand:

* how many companies are present
* which stock symbols are available
* whether there are missing values or duplicates

---

## 🔹 Data Analysis & Visualization

Before building the model, I analyzed the data properly:

* Checked shape and columns of dataset
* Verified null values and duplicates
* Observed different company stocks

Then I plotted graphs for some companies to see:

* how stock prices change over time
* difference between opening and closing prices

This step is important because it helps to understand trends before applying ML.

---

## 🔹 Data Preprocessing

After analysis, I selected one company (Yahoo - YHOO) for prediction.

Steps I followed:

1. Extracted closing price data
2. Converted data into numpy array
3. Applied **MinMaxScaler** to normalize values (0 to 1 range)
4. Split data into:

   * 80% training
   * 20% testing

---

## 🔹 Feature Engineering

Since this is time-series data, I cannot directly give raw data to the model.

So I created a function:

```python id="67r71w"
process_data()
```

This function converts data into sequences like:

* Input → previous values
* Output → next value

Example:
If input is `[x1, x2]` → output is `x3`

This helps the model learn patterns over time.

---

## 🔹 Model Building

I built a hybrid deep learning model using:

* **GRU layer (256 units)** → captures sequential patterns
* **LSTM layer (256 units)** → remembers long-term dependencies
* **Dropout (0.4)** → reduces overfitting
* **Dense layers** → final prediction

Why GRU + LSTM?
Because both are powerful for time-series, and combining them improves learning.

---

## 🔹 Model Training

* Loss function: Mean Squared Error (MSE)
* Optimizer: Adam
* Epochs: 100
* Batch size: 128

Also used:

* **ModelCheckpoint** → saves best model
* **ReduceLROnPlateau** → reduces learning rate when needed

---

## 🔹 Prediction & Evaluation

After training:

* Predicted stock prices on test data
* Converted values back to original scale
* Compared predicted vs actual values

Used:

* **R² Score** to measure accuracy

Also plotted graphs:

* Blue → actual prices
* Red → predicted prices

This helps visually understand model performance.

---

## 🔹 Final Output

* Generated prediction results
* Saved into `results.csv` file
* Contains actual + predicted values together

---

## 🔹 What I Learned

* How to handle real-world datasets
* Importance of preprocessing and scaling
* How time-series data works
* How GRU and LSTM models are used
* How to evaluate ML models

---

## 🔹 Limitations

* Stock market is unpredictable
* Model accuracy is not 100%
* Only one feature (closing price) used
* More features (volume, news, etc.) can improve results

---

## 🔹 How to Run

1. Install required libraries:

```bash id="9vc8km"
pip install numpy pandas matplotlib scikit-learn tensorflow keras
```

2. Place dataset files in same folder

3. Run the Python file

---

## 🔹 Conclusion

This project is a basic implementation of stock market prediction using deep learning. It shows how models can learn patterns from historical data, but real-world prediction still depends on many external factors.

---







