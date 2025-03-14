# City Air - Dsa210-project
## Project Overview
This project analyzes the relation between Tuzla’s air quality and my sleep patterns over a three months period. By using publicly available air pollution data with my personal sleep data from a mobile app, I aim to explore whether the changes in air quality impacts my sleep duration and quality. From data collection to using data visualization and statistical analysis, I will assess trends and test hypotheses about the topic. I aim to provide personal insights into how environmental factors affect sleep and contribute to a broader understanding of urban health challenges.

## Motivation
From coming from countryside onto living in a metropolitan city like Istanbul, I wondered how enviromental factors like air pollution may be affecting my sleep. By relying on objective, publicly available datasets and my own sleep records from mobile apps, I aim to take a data-driven approach to a key aspect of well-being. The findings may help to optimize my sleep habits as well as raise awareness about the impact of air pollution on health.

## Learning Objectives
**1. Analyzing the Relation Between Sleep & Air Quality:** I will investigate whether poor air quality is associated with reduced sleep duration or lower sleep quality.

**2. Controlling for External Factors:** I will enrich the analysis with weather data and temperatures to distinguish air quality effects from other environmental conditions.

**3. Identifying Thresholds:** I will find out if specific pollution levels for the specific air pollutants(e.g., PM2.5, NO₂) significantly impact sleep patterns.

**4. Predictive Modeling:** I will use regression models to assess and predict how air pollution influences sleep.

**5. Apply Data Science Techniques:** I will utilize data collection, visualization, and statistical analysis skills learned in DSA 210.

## Dataset
The dataset will consist of:

**City Air Quality Data:**
Daily measurements of PM2.5, PM10, NO₂, SO₂, CO, O3 from:

Istanbul Hava Kalitesi İzleme Merkezi, IQAir

**Personal Sleep Data:**
Sleep duration and quality scores collected from a sleep tracking app.

**Additional Enrichment:**
Weather data (temperature, humidity, wind) from Hava Durumu app to control for confounding variables.

**Tools & Technologies:**
Python: For data processing and statistical analysis.

Pandas & NumPy: For data cleaning and manipulation.

Matplotlib & Seaborn: For data visualization.

SciPy & Statsmodels: For hypothesis testing and regression analysis.

Jupyter Notebook: For exploratory data analysis.

## Analysis Plan
**Data Collection:**
Import daily air quality, sleep, and weather data into a Pandas DataFrame.
Align datasets by date for consistency.

**Data Cleaning:**
Handle missing values, remove outliers, and standardize units.

**Visualization:**
Time series plots to observe trends in sleep duration vs. air quality.
Scatter plots to explore potential correlations.
Heatmaps to show relationships between multiple variables.

**Hypothesis Testing:**
Example hypotheses:
H₀: Air quality does not affect sleep duration or quality.
Hₐ: Higher pollution levels correlate with shorter or lower-quality sleep.
Perform statistical tests to validate findings.

**Trend Analysis & Prediction:**
Develop a regression model to predict sleep quality based on air pollution levels.
Identify patterns such as seasonal changes in air quality and their impact on sleep.
Example Analysis
For instance, I will compare my average sleep duration on days with “Good” air quality vs. days with “Unhealthy” air quality. I will also create a scatter plot with PM2.5 levels on the x-axis and sleep quality scores on the y-axis to identify potential trends. If a clear negative correlation exists, it would suggest that air pollution might contribute to poorer sleep.

## Conclusion
By the end of this project, I hope to answer:

Does air pollution in Istanbul significantly affect sleep duration or quality?

Are there specific pollutant thresholds where sleep is noticeably impacted?

How do weather conditions interact with air pollution’s effects on sleep?

Can a predictive model be developed to estimate sleep quality based on environmental conditions?

This project will not only provide insights into how air quality impacts personal health but also serve as a real-world application of data science techniques, blending personal data with urban environmental analysis.
