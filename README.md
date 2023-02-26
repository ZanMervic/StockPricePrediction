# Stock Price Prediction with LSTM

This Python program uses a Long Short-Term Memory (LSTM) neural network to predict the closing price of a stock, in this case, Apple Inc (AAPL), using historical data.

## Libraries Used
- numpy
- pandas
- matplotlib
- yfinance
- datetime
- math
- sklearn
- keras

## Usage
1. Create a python virtual environment
```
python -m venv <venv_name>
```

2. Activate the environment (different for each platform)
```
bash/zsh
$ source <venv>/bin/activate

fish
$ source <venv>/bin/activate.fish

csh/tcsh
$ source <venv>/bin/activate.csh

PowerShell
$ <venv>/bin/Activate.ps1

cmd.exe
C:\> <venv>\Scripts\activate.bat

PowerShell
PS C:\> <venv>\Scripts\Activate.ps1
```

3. Install the libraries in requirements.txt file using:

```
pip install -r requirements
```

## Dataset
This program downloads stock data for Apple Inc (AAPL) from Yahoo Finance for a 10-year timeframe.

## Data preparation
1. The program extracts the closing prices from the stock data and converts it to a numpy array.
2. The training data is scaled using the MinMaxScaler from sklearn.
3. The program uses the last 55 days of the scaled training data to predict the 60th day (5 days in the future).
4. The training data is split into x_train and y_train data sets, where x_train has 55 values to predict the 60th value.
5. The x_train data set is reshaped into a 3-dimensional numpy array, where the dimensions are samples, time steps, and features.

## Model
The LSTM neural network has the following layers:

1. LSTM layer with 50 neurons, return_sequences=True, and input_shape=(x_train.shape[1], 1)
2. Dropout layer with a rate of 0.2
3. LSTM layer with 50 neurons, return_sequences=True
4. Dropout layer with a rate of 0.2
5. LSTM layer with 50 neurons, return_sequences=False
6. Dropout layer with a rate of 0.2
7. Dense layer with 25 neurons
8. Dense layer with 1 neuron

The model optimizer is Adam, and the loss function is mean squared error. The batch size is 10, and the number of epochs is 4.