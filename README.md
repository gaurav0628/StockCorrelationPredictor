**INTRODUCTION**

Auto Regressive models such as Auto Regressive Integrated Moving Averages (ARIMA), Seasonal Auto Regressive Integrated Moving Averages with extra variables (SARIMAX) have been used for timeseries forecasting. Recurrent Neural Networks is cutting edge technology that can challenge traditional models in time series forecasting. In this project, a hybrid of Seasonal Auto Regressive model and Long Short-Term Memory Recurrent Neural Network is proposed which can be used for determining stock price correlation coefficient. This model aims to capture linear residual values using Auto Regressive models and nonlinear residual values using Long Short-Term Memory Recurrent Neural Network for Stock Correlation Coefficient prediction.

**Conceptual Design :**

![System Architecture](https://github.com/gauravUFL/StockCorrelationPredictor/blob/master/Architecture.png)

Following modules are included in the code. Each one of ehich is described here:

*A. Data Scraping Module*

Collects data from internet. The data is of tickers for SP 500 companies. One needs a keys file to run this module. Alpha Vantage Keys.txt file with your Alpha Vantage Keys should be created. Or you can download data from some other source and just skip this module.

*B. Data Wrangling Module*

Cleans and preprocesses data before running the model. Looks for correlations manages null/void values. Also data for training and testing is separated here.

*C. ARIMA Module*

Trains ARIMA model and saves the output vector. This model captures linear tendencies in training data.

*D. SARIMAX Module*

Trains SARIMAX model and saves the output vector. This model captures linear tendencies in training data.

*E. LSTM Module*

Takes output vector from ARIMA/SARIMAX and trains the model to predict the coefficeint values. This model captures non linear tendencies in training data.

![LSTM Cell](https://github.com/gauravUFL/StockCorrelationPredictor/blob/master/LSTM%20Cell.png)

*F. TEST_ASSET Module (SARIMAX-LSTM/ARIMALSTM)*

Tests the model generated in LSTM module using testing data.

![ARIMA-LSTM Results](https://github.com/gauravUFL/StockCorrelationPredictor/blob/master/ARIMA%20Res.png)
![SARIMAX-LSTM Results](https://github.com/gauravUFL/StockCorrelationPredictor/blob/master/SARIMAX%20Res.png)

*G. Model Evaluator Module*

Compares SARIMAX/ARIMA - LSTM to existing classical models such as Single Index, Historical, Constant Correlation

![Result Comparison with other models](https://github.com/gauravUFL/StockCorrelationPredictor/blob/master/evaluations.png)



