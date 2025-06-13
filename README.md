# Covid-Data-Analysis
COVID-19 data analysis and visualization using Python

[Code.txt](https://github.com/user-attachments/files/20725618/Code.txt)
import pandas as pd
import matplotlib.pyplot as plt
<br>
df = pd.read_csv("covid-data.csv")
india_df = df[df['location'] == 'India'].copy()
india_df['date'] = pd.to_datetime(india_df['date'])

plot_df = india_df.dropna(subset=['total_cases', 'total_deaths'])

plt.figure(figsize=(10, 6))
plt.plot(plot_df['date'], plot_df['total_cases'], label='Total Cases', color='blue')
plt.plot(plot_df['date'], plot_df['total_deaths'], label='Total Deaths', color='red')
plt.xlabel('Date')
plt.ylabel('Count')
plt.title('COVID-19 Total Cases and Deaths in India Over Time')
plt.legend()
plt.grid(True)

# Save the plot
plt.savefig("covid_output.png")
![covid_output](https://github.com/user-attachments/assets/010c5915-29cf-431a-9ac5-249b953c51e6)
