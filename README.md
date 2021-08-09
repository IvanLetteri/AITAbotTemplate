# Statistical_Modeling_for_Time_Series_Forecasting
The DeFi tokens are analysed using popular statistical models such as **SARIMA**, **ETS** and **GARCH**. Additionally, a powerful open source forecasting package from Facebook, called **Prophet**, is also explored and used to generate forecasts.

# Blogs 
If you prefer an in-depth explanation for the code in this repository, I would recommend going through the followig articles where I have explained my approch in detail - 
- [Statistical Modeling of Time Series Data Part 1: Data Preparation and Preprocessing](https://ivanletteri.it/statistical-modeling-of-time-series-data-part-1-data-preparation-and-preprocessing)
- [Statistical Modeling of Time Series Data Part 2: Exploratory Data Analysis](https://ivanletteri.it/statistical-modeling-of-time-series-data-part-2-exploratory-data-analysis)
- [Statistical Modeling of Time Series Data Part 3: Forecasting Stationary Time Series using SARIMA](https://ivanletteri.it/statistical-modeling-of-time-series-data-part-3-forecasting-stationary-time-series-using-sarima)
- [Statistical Forecasting of Time Series Data Part 4: Forecasting Volatility using GARCH](https://ivanletteri.it/statistical-forecasting-of-time-series-data-part-4-forecasting-volatility-using-garch)
- [Statistical Forecasting for Time Series Data Part 5: ARMA+GARCH model for Time Series Forecasting](https://medium.com/towards-artificial-intelligence/statistical-forecasting-for-time-series-data-part-5-arma-garch-model-for-time-series-forecasting-98beeedcfba8)
- [Statistical Forecasting for Time Series Data Part 6: Forecasting Non-Stationary Time Series using ARIMA](https://medium.com/towards-artificial-intelligence/statistical-forecasting-for-time-series-data-part-6-forecasting-non-stationary-time-series-using-9acc28c39db9)

# Acquiring Data and Data Preprocessing
The **S&amp;P 500** stock market **Prices** are scrapped from Yahoo's `yfinance` library in python. The data is then cleaned and used to build 2 other important time series: S&amp;P 500 **Returns** (percent change in Prices) and **Volatility** (Magnitude of Returns). All these steps are in the `Preprocessing.ipynb` notebook.

# Exploratory Data Analysis
The 3 time series from above are explored using techniques like:
- Line and Box Plots
- Density Curves
- Decomposition Plots (Additive and Multiplicative)
- Smoothing Functions (Moving Average Smoothing)
- Correlation Plots (ACF and PACF)
- Stationarity Checks (ADF and KPSS tests)

The insights gained from these exploratory techniques help the model building process. All the steps here are in `Visualization and EDA.ipynb` notebook.

# SARIMA
## SARIMA on S&amp;P 500 Returns
Here, the SARIMA class of models are used to model and forecast a stationary time series: S&amp;P 500 Returns. The steps for this model are in `Returns Models/SARIMA For SPX Returns.ipynb` notebook.

## SARIMA on S&amp;P 500 Prices
Here, the same models are used for a non-stationary time series: S&amp;P 500 Prices. The trick used (data transformation) to model this series successfully and other details of the model are in `Prices Models/ARMA Model for SPX Prices.ipynb` notebook.

# ETS
The notebook `Returns Models/Exponential Smoothing Models for SPX Returns.ipynb` contains all 3 types of ETS models fitted on S&amp;P 500 Returns

# GARCH
The Volatility of the S&amp;P 500 Returns are modeled and forecasted using this model. The code for the same is in `Volatility Models/GARCH for SPX Volatility.ipynb` notebook.

# ARMA-GARCH
Here a combination of the 2 models (ARMA and GARCH) is used to model the S&amp;P 500 Returns. First the ARMA model is used to fit the Returns, and later the residuals generated by the ARMA model are modeled using the GARCH model. The code for this is in `Returns Models/ARMA-GARCH For SPX Returns.ipynb` notebook

# Facebook Prophet
Facebook has developed a powerful time series forecasting tool called Prophet. In this analysis only a subset of its features are explored. The official [documentation](https://facebook.github.io/prophet/docs/quick_start.html) of the package contains many many useful features that can assist almost anyone tackling a time series data. The code used to fit the prophet model to this data is in the notebook: `Prophet Models/Prophet for SPX Prices and Retruns.ipynb`.

**Note:** Most of the packages used in this analysis are standard and will be present in most python environments. For downloading prophet locally you can follow the steps [here](https://facebook.github.io/prophet/docs/installation.html#python) or just run the `!pip install fbprophet` command in a [Google Colab](https://colab.research.google.com/notebooks/intro.ipynb#recent=true) code cell if you are working there. 
