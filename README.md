This project consists of two separate analyses using R:
	1.	Annual Mean Temperature Analysis (cet_temp):
Analyze and model historical annual mean temperature data (1900–2021) using ARIMA models. This includes data visualization, stationarity checks (differencing), ACF/PACF analysis, and model diagnostics (Ljung-Box test).
	2.	Monthly Average House Prices Forecasting (em_house):
Examine and forecast monthly average house prices using SARIMA models. The analysis involves checking for seasonality, applying seasonal and regular differencing, model fitting, residual diagnostics, and forecasting the next six months of house prices.

Project Structure
	•	cet_temp.Rmd
Contains the analysis for the annual mean temperature data. Key components include:
	•	Time series creation from temperature data.
	•	Plotting the series along with ACF and PACF.
	•	Fitting and comparing multiple ARIMA models.
	•	Using a custom LB_test function to perform the Ljung-Box test for residual diagnostics.
	•	em_house.Rmd
Contains the analysis for the monthly average house prices. This file includes:
	•	Time series creation from house price data.
	•	Seasonal decomposition using STL.
	•	Seasonal and regular differencing.
	•	Fitting various SARIMA models with custom residual diagnostic tests.
	•	A custom function LB_test_SARIMA to compute Ljung-Box test P-values for SARIMA residuals.
	•	A helper function sarima_results to iterate over different model parameters and identify the best-fitting model.
	•	Forecasting future house prices with visualization of confidence intervals.
	•	Data Files:
	•	cet_temp dataset: Contains temperature data with the column avg_annual_temp_C.
	•	em_house_prices.csv: Contains house prices data with the column average_price_gbp.



 Project Details

Annual Mean Temperature Analysis (cet_temp)
	•	Data: Annual mean temperature data from 1900 to 2021.
	•	Analysis Highlights:
	•	Creation of a time series object using the ts() function.
	•	Visualization of the time series and its ACF/PACF plots.
	•	Application of differencing to achieve stationarity.
	•	Fitting various ARIMA models (e.g., ARIMA(1,1,0), ARIMA(0,1,1), etc.).
	•	Diagnostic testing using a custom Ljung-Box test function (LB_test) to assess model residuals.

Monthly Average House Prices Analysis (em_house)
	•	Data: Monthly average house prices data.
	•	Analysis Highlights:
	•	Construction of a time series object from house prices.
	•	Identification and visualization of seasonality using STL decomposition.
	•	Application of seasonal and regular differencing.
	•	Fitting multiple SARIMA models and evaluating their performance using ACF, PACF, and Ljung-Box tests.
	•	Iterative model selection using the sarima_results function to identify optimal parameters.
	•	Forecasting future house prices (next 6 months) with confidence intervals.

 Custom Functions
	•	LB_test:
    Computes P-values for the Ljung-Box test over a range of lags for ARIMA models. Useful for checking residual autocorrelation.
	•	LB_test_SARIMA:
    An extension of the Ljung-Box test function tailored for SARIMA model residuals.
	•	sarima_results:
    Iterates over combinations of SARIMA parameters, fits models, and selects those that pass the Ljung-Box test while ranking them by AIC/BIC.


Prerequisites

Ensure you have the following installed:
	•	R (version 4.0 or higher)
	•	RStudio (recommended for ease of use)
	•	Required R packages:
	•	readr
	•	forecast
	•	ggplot2
	•	(Other packages may be required as referenced in the R Markdown files)
