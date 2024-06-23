#Stock-Analysis-Apple-Amazon-Google-Microsoft
This Jupyter Notebook provides a comprehensive analysis of stock prices for selected companies over a period of five years. The primary focus is on data collection, processing, and visual analysis of stock price changes over time.

Table of Contents
Data Collection
Data Preprocessing
Analysis of Price Changes
Visualization
Correlation Analysis
Conclusions
Data Collection
The data for this analysis is collected from CSV files containing stock prices for individual companies over five years. The companies included in this analysis are Apple (AAPL), Amazon (AMZN), Google (GOOG), and Microsoft (MSFT). The glob module is used to retrieve all CSV files from the specified directory, ensuring that all relevant files are included for the analysis.

Data Preprocessing
Once the data is collected, it is loaded and concatenated into a single DataFrame for analysis. Any missing values are identified and handled appropriately, and the data types of each column are checked and converted if necessary. This ensures that the dataset is clean and ready for analysis. The append method from pandas is utilized to combine the data from multiple files into one cohesive DataFrame.

Analysis of Price Changes
The change in stock prices over time is analyzed by calculating the percentage change in closing prices for each stock. This involves creating a pivot table with dates as the index and stock names as columns, and then calculating the percentage change from one day to the next for each stock. This step is crucial for understanding the volatility and performance of each stock over the specified period.

Visualization
Various visualizations are employed to understand the distribution and relationship between stock price changes. PairGrid from Seaborn is used to create detailed pairwise plots. These plots include histograms on the diagonals to show the distribution of percentage changes, scatter plots on the lower triangle to show relationships between pairs of stocks, and KDE (Kernel Density Estimate) plots on the upper triangle to show the density of the data points.

Correlation Analysis
The correlation between the percentage changes in stock prices of different companies is calculated to understand their relationship. This helps in identifying how the stocks move in relation to each other, providing insights into whether they tend to move together or independently. Correlation matrices are used to summarize these relationships.

Conclusions
The analysis concludes with insights into the linear relationships and correlations between the stock price changes of different companies. For instance, it was observed that there is a linear relationship to some extent between the percentage changes in the closing prices of Apple and Amazon stocks. These insights can be valuable for investors and analysts looking to understand market dynamics and make informed decisions.

Dependencies
The following Python packages are required to run the notebook: pandas, numpy, matplotlib, seaborn, glob, and warnings. These packages are imported at the beginning of the notebook to ensure all necessary tools are available for data manipulation, visualization, and analysis.
