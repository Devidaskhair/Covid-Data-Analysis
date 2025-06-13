# Covid-Data-Analysis
COVID-19 data analysis and visualization using Python


import pandas as pd
import matplotlib.pyplot as plt
<br>
df = pd.read_csv("covid-data.csv")
<br>
india_df = df[df['location'] == 'India'].copy()
<br>
india_df['date'] = pd.to_datetime(india_df['date'])
<br>

plot_df = india_df.dropna(subset=['total_cases', 'total_deaths'])
<br>

plt.figure(figsize=(10, 6))
<br>
plt.plot(plot_df['date'], plot_df['total_cases'], label='Total Cases', color='blue')
<br>
plt.plot(plot_df['date'], plot_df['total_deaths'], label='Total Deaths', color='red')
<br>
plt.xlabel('Date')
<br>
plt.ylabel('Count')
<br>
plt.title('COVID-19 Total Cases and Deaths in India Over Time')
<br>
plt.legend()
<br>
plt.grid(True)
<br>

plt.savefig("covid_output.png")
<br>
![covid_output](https://github.com/user-attachments/assets/010c5915-29cf-431a-9ac5-249b953c51e6)
