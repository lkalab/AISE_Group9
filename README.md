# AISE_Group9
This repository contains 4 files: the dataset used in this project as a csv, this README file, and the notebooks for both the GRU and LSTM Models.

# **Crop Yield Prediction with LSTMs**

## **Overview**  
This project implements a Long Short-Term Memory (LSTM) model and a Gated Recurrent Unit (GRU) Model to predict crop yield based on historical data. The model uses environmental factors such as temperature and humidity to analyze and forecast crop yields for specific crops.

---

## **Requirements**  
Ensure the following tools and libraries are installed:  
- **Python**: 3.x  
- **TensorFlow**: 2.x  
- **Keras**  
- **Pandas**  
- **NumPy**  
- **Matplotlib** (optional, for visualization)  
- **scikit-learn** (optional, for hyperparameter tuning via GridSearchCV)  

---

## **Data**  
The project expects a CSV file named `crop_yield_dataset.csv` with the following columns:  
- **Date**: (e.g., YYYY-MM-DD)  
- **Crop_Type**: Type of crop (e.g., rice, wheat)  
- **Crop_Yield**: Historical crop yield data  
- **Temperature**: Environmental temperature  
- **Humidity**: Environmental humidity  

The **Date** column should be set as the index, and the **Crop_Type** column will be excluded during preprocessing. You can select specific crops for analysis by modifying the script.

---

## **Functionality**  

### 1. **Data Loading and Preprocessing**  
- Reads the `crop_yield_dataset.csv` using `pandas`.  
- Sets **Date** as the index for time-series analysis.  
- Filters the data to train individual models for specific crops (e.g., rice or wheat).  
- Scales the data using **MinMaxScaler** for optimal performance.

### 2. **Model Building**  
- Defines an LSTM model using the **Keras Sequential API**:  
  - Includes one or more LSTM layers with user-specified units.  
  - Employs a dense output layer with a single neuron to predict crop yield.  
- Compiles the model with the Adam optimizer and Mean Squared Error (MSE) loss function.

### 3. **Hyperparameter Tuning (Optional)**  
- Uses **GridSearchCV** (optional) for hyperparameter optimization.  
- Parameters explored:  
  - Number of LSTM layers.  
  - Units in each LSTM layer.  
  - Number of epochs.  
- Outputs the combination with the lowest Mean Absolute Error (MAE) on the validation set.

### 4. **Training and Evaluation**  
- Splits data into training and validation sets.  
- Trains the model for a user-specified number of epochs.  
- Evaluates the model using MAE and prints the best parameters (if hyperparameter tuning is performed).  

---
