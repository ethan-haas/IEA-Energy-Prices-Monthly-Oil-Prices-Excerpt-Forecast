IEA Energy Prices - Monthly Oil Prices Excerpt Forecast.ipynb

This Jupyter notebook contains Python code for forecasting monthly oil prices using a Monte Carlo simulation. The data used in this code is from the International Energy Agency (IEA) and is available on their website (https://www.iea.org/data-and-statistics/data-product/monthly-oil-price-statistics-2#data-sets). The dataset used is labeled "raw".

Libraries Used:

pandas - used for reading and preprocessing the data
numpy - used for generating random monthly returns for the Monte Carlo simulation
plotly - used for creating interactive visualizations

Functions Used:

monte_carlo_sim(df, country, product, num_simulations=1000000, num_periods=12)
This function takes in the preprocessed data, the country and product for which the forecast is to be made, and the number of simulations to be run and the number of periods for which to simulate the data. It first filters the data for the specified country and product, and then calculates the mean and standard deviation of the monthly returns. Using these values, it generates random monthly returns for the specified number of simulations and periods, and then uses them to calculate the future values for each simulation. Finally, it returns the mean prediction, the lower and upper predictions for the 95th and 75th percentiles. If the filtered dataframe is empty, it returns None for all outputs.

plot_forecast(df, country, product, mean_prediction, lower_prediction_95, upper_prediction_95, lower_prediction_75,upper_prediction_75)
This function takes in the preprocessed data, the country and product for which the forecast was made, and the mean prediction, lower and upper predictions for the 95th and 75th percentiles. It first filters the data for the specified country and product and extracts the start and end dates. Then, it creates traces for the actual data, the mean prediction, and the lower and upper predictions for the 95th and 75th percentiles. Finally, it creates an interactive plot using plotly and returns it. If the filtered dataframe is empty, it prints a message saying that no data is available.

Code Workflow:

Read in the data from the Excel sheet labeled "raw"
Convert the TIME column to a pandas datetime object
Group the data by COUNTRY and PRODUCT and sort by TIME
Reset the index of the grouped dataframe
Call the monte_carlo_sim function for the desired country and product
Call the plot_forecast function using the output from the monte_carlo_sim function
Note: This code was originally created in Google Colaboratory, and the notebook can be accessed using the link provided in the code.
