<h1 style="color:blue; font-weight:bold">IEA Energy Prices - Monthly Oil Prices Excerpt Forecast.ipynb</h1>
This Jupyter notebook contains Python code for forecasting monthly oil prices using a Monte Carlo simulation. The data used in this code is from the International Energy Agency (IEA) and is available on their website (https://www.iea.org/data-and-statistics/data-product/monthly-oil-price-statistics-2#data-sets). The dataset used is labeled "raw".


<h2 style="color:blue; font-weight:bold">Libraries Used:</h2>
pandas - used for reading and preprocessing the data numpy - used for generating random monthly returns for the Monte Carlo simulation plotly - used for creating interactive visualizations



<h2 style="color:blue; font-weight:bold">Functions Used:</h2>
monte_carlo_sim(df, country, product, num_simulations=1000000, num_periods=12) This function takes in the preprocessed data, the country and product for which the forecast is to be made, and the number of simulations to be run and the number of periods for which to simulate the data. It first filters the data for the specified country and product, and then calculates the mean and standard deviation of the monthly returns. Using these values, it generates random monthly returns for the specified number of simulations and periods, and then uses them to calculate the future values for each simulation. Finally, it returns the mean prediction, the lower and upper predictions for the 95th and 75th percentiles. If the filtered dataframe is empty, it returns None for all outputs.

plot_forecast(df, country, product, mean_prediction, lower_prediction_95, upper_prediction_95, lower_prediction_75,upper_prediction_75) This function takes in the preprocessed data, the country and product for which the forecast was made, and the mean prediction, lower and upper predictions for the 95th and 75th percentiles. It first filters the data for the specified country and product and extracts the start and end dates. Then, it creates traces for the actual data, the mean prediction, and the lower and upper predictions for the 95th and 75th percentiles. Finally, it creates an interactive plot using plotly and returns it. If the filtered dataframe is empty, it prints a message saying that no data is available.


<h2 style="color:blue; font-weight:bold">Code Workflow:</h2>

1.) Read in the data from the Excel sheet labeled "raw"

2.) Convert the TIME column to a pandas datetime object

3.) Group the data by COUNTRY and PRODUCT and sort by TIME

4.) Reset the index of the grouped dataframe 

5.) Call the monte_carlo_sim function for the desired country and product

6.) Call the plot_forecast function using the output from the monte_carlo_sim function


Note: This code was originally created in Google Colaboratory, and the notebook can be accessed using the link provided in the code.



<h2 style="color:blue; font-weight:bold">Examples of output plots (plots are interactive while using jupyter notbook):</h2>

<h3 style="color:blue; font-weight:bold">United States</h3>

![newplot (9)](https://user-images.githubusercontent.com/88012037/230486943-c4ece611-f4d9-4e92-a8d5-00bc53d637b1.png)
![newplot (8)](https://user-images.githubusercontent.com/88012037/230486965-8c575616-c07f-42a0-a455-8386093c2247.png)
![newplot (7)](https://user-images.githubusercontent.com/88012037/230487000-bb246c57-c115-4ce8-ba5c-2b767cdfcfcf.png)


<h3 style="color:blue; font-weight:bold">United Kingdom</h3>

![newplot (6)](https://user-images.githubusercontent.com/88012037/230487096-bb205386-af5d-458e-b197-22812b43fccb.png)
![newplot (5)](https://user-images.githubusercontent.com/88012037/230487141-04d02886-9815-42da-8d93-72ca211eff13.png)
![newplot (4)](https://user-images.githubusercontent.com/88012037/230487714-3b96ea9f-0cc7-4eaa-af06-1b4d740c2e4b.png)


<h3 style="color:blue; font-weight:bold">Canada</h3>

![newplot (3)](https://user-images.githubusercontent.com/88012037/230487421-0e1e2800-5a0b-4cfd-8326-2bb1c0f086ab.png)
![newplot (2)](https://user-images.githubusercontent.com/88012037/230487364-0746d4c6-4005-47d2-85ae-c1ab8be294bd.png)
![newplot (1)](https://user-images.githubusercontent.com/88012037/230487349-24e1cda5-c73a-41e7-bbee-07296ffec4d6.png)


