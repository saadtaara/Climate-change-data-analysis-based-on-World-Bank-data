# Climate-change-data-analysis-based-on-World-Bank-data
analysis of Climate change data analysis based on World Bank data for better decision making
import pandas as pd
import matplotlib.pyplot as plt

# World Bank climate data
data = {
    "country": ["China", "China", "China", "China", "China", "China", "China"],
    "year": [2010, 2011, 2012, 2013, 2014, 2015, 2016],
    "population": [1338612345, 1342841882, 1347075921, 1351310163, 1355532573, 1359744253, 1363955993],
    "agriculture": [12.2, 12.4, 12.6, 12.8, 13.0, 13.2, 13.4],
    "forestry": [3.2, 3.3, 3.4, 3.5, 3.6, 3.7, 3.8],
    "gas_emission": [7.8, 8.0, 8.2, 8.4, 8.6, 8.8, 9.0],
    "gdp": [5493.2, 5728.4, 6012.3, 6332.1, 6680.9, 7061.8, 7471.4],
    "livestock": [4.2, 4.3, 4.4, 4.5, 4.6, 4.7, 4.8],
    "electricity": [3.5, 3.6, 3.7, 3.8, 3.9, 4.0, 4.1],
}

df = pd.DataFrame(data)

# Calculate correlation coefficients
correlation = df.corr()

# Create a correlation matrix heatmap
plt.matshow(correlation, cmap="coolwarm")
plt.title("Correlation Matrix of China's Population and Climate Activities")

# Annotate the heatmap with the correlation coefficients
for i in range(len(correlation.columns)):
    for j in range(len(correlation.columns)):
        plt.text(
            i,
            j,
            f"{correlation.iloc[i, j]:.2f}",
            ha="center",
            va="center",
            fontsize=8,
        )

plt.xticks(range(len(correlation.columns)), correlation.columns, rotation=45)
plt.yticks(range(len(correlation.columns)), correlation.columns)
plt.show()
