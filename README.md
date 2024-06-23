# Stock-Analysis-Apple-Amazon-Google-Microsoft-
Stock Price Analysis
This Jupyter Notebook provides a comprehensive analysis of stock prices for selected companies over a period of five years. The primary focus is on data collection, processing, and visual analysis of stock price changes over time.

Table of Contents
Data Collection
Data Preprocessing
Analysis of Price Changes
Visualization
Correlation Analysis
Conclusions
Data Collection
The data for this analysis is collected from CSV files containing stock prices for individual companies over five years. The companies included in this analysis are:

Apple (AAPL)
Amazon (AMZN)
Google (GOOG)
Microsoft (MSFT)
python
Copy code
import pandas as pd
import numpy as np
import glob

# List of company data files
company_list = [
    'Z:\\3.. S_&_P\\Datasets\\individual_stocks_5yr\\AAPL_data.csv',
    'Z:\\3.. S_&_P\\Datasets\\individual_stocks_5yr\\AMZN_data.csv',
    'Z:\\3.. S_&_P\\Datasets\\individual_stocks_5yr\\GOOG_data.csv',
    'Z:\\3.. S_&_P\\Datasets\\individual_stocks_5yr\\MSFT_data.csv'
]
Data Preprocessing
The data is loaded and concatenated into a single DataFrame for analysis. Any missing values and data types are checked and handled appropriately.

python
Copy code
# Concatenate data from multiple files
all_data = pd.DataFrame()
for file in company_list:
    current_df = pd.read_csv(file)
    all_data = current_df.append(all_data, ignore_index=True)

# Check for missing values
all_data.isnull().sum()

# Check data types
all_data.dtypes
Analysis of Price Changes
The change in stock prices over time is analyzed by calculating the percentage change in closing prices for each stock.

python
Copy code
# Calculate percentage change in closing prices
closing_price = all_data.pivot_table(index='date', columns='Name', values='close')
for col in closing_price.columns:
    closing_price[col + '_pct_change'] = (closing_price[col] - closing_price[col].shift(1)) / closing_price[col].shift(1) * 100
Visualization
Various visualizations are used to understand the distribution and relationship between stock price changes. PairGrid from Seaborn is used for detailed pairwise plots.

python
Copy code
import seaborn as sns
import matplotlib.pyplot as plt

# PairGrid visualization
g = sns.PairGrid(data=clsing_p)
g.map_diag(sns.histplot)
g.map_lower(sns.scatterplot)
g.map_upper(sns.kdeplot)
plt.show()
Correlation Analysis
The correlation between the percentage changes in stock prices of different companies is calculated to understand their relationship.

python
Copy code
# Calculate correlation
clsing_p.corr()
Conclusions
The analysis concludes with insights into the linear relationships and correlations between the stock price changes of different companies.

python
Copy code
"""
Conclusion:
While comparing 'AAPL_close_pct_change' to 'AMZN_close_pct_change', it shows a linear relationship to some extent.
"""
Dependencies
The following Python packages are required to run the notebook:

pandas
numpy
matplotlib
seaborn
glob
warnings
python
Copy code
# Import necessary packages
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import glob
import warnings
from warnings import filterwarnings
filterwarnings('ignore')
