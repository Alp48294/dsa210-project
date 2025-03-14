# City Air - Dsa210-project
## Project Overview
In this project I will explore how does Istanbul's air quality impacts my sleeping quality over the next semester. I will use publicly available city data on air pollution with my own step count (maybe even my sleep duration data from sleep tracking app) to uncover whether quality of the air correspond to changes with my outdoor activity time on the campus. I will use data visualization and statistical analysis to find patterns and check hypothesis
## Motivation
After coming from countryside, I've often wondered if the quality of an metropolitan city's air affects how much I move around the city.
I am exploring how Istanbul's urban air quality impacts my daily physical activity. Living in a large metropolitan area, I've often wondered if the quality of air affects how much I move around the city. This project combines my interest in urban environmental health with personal fitness data to answer a question that has both personal relevance and broader public health implications.
Data Sources and Collection
This project will integrate multiple data sources:

## Primary Air Quality Data:

Daily air quality measurements (PM2.5, PM10, NO₂) from the Istanbul Metropolitan Municipality Open Data Portal (data.ibb.istanbul)
World Air Quality Index (WAQI) historical data for cross-validation


Personal Activity Data:

Daily step count collected through my smartphone's health app
Location data (anonymized to district level) to correlate with specific air monitoring stations


Data Enrichment:

Weather data from OpenWeatherMap API (temperature, humidity, precipitation)
Calendar data (weekdays/weekends, holidays) to account for routine changes



I'll collect this data using a combination of API access (where available) and manual exports, automating the process where possible using Python scripts for regular collection.
Planned Analysis
My analysis will progress through several stages:
Exploratory Data Analysis

Temporal patterns in both air quality and activity data
Distribution analysis of key variables
Correlation analysis between pollutant levels and step counts
Geographic visualization comparing different districts (particularly Tuzla area)

Statistical Analysis

Hypothesis testing:

H₀: There is no significant relationship between air quality metrics and daily step count
H₁: Days with poorer air quality show statistically significant reductions in step count


ANOVA to compare activity levels across different air quality categories
Multiple regression analysis controlling for weather variables and day of week

Machine Learning Approaches

Develop prediction models using:

Linear regression models
Decision trees to identify threshold values
Time series forecasting to predict activity levels based on forecasted air quality


Feature importance analysis to identify which pollutants have the strongest impact

Expected Findings
I expect to discover:

Threshold levels of specific pollutants that correlate with significant activity reduction
Seasonal patterns in both air quality and its impact on activity
The relative importance of different pollutants on activity decisions
The effectiveness of weather as a control variable

Limitations and Future Work

Sample size limitations (data from a single individual)
Potential confounding variables beyond weather and calendar
Limited geographic specificity of public air quality monitors

Future work could include:

Expanding to a multi-participant study
Incorporating subjective survey data on perception of air quality
Developing a simple application to provide personalized activity recommendations based on air quality forecasts

Technical Implementation
This project will be implemented entirely in Python, utilizing:

Pandas and NumPy for data manipulation
Matplotlib, Seaborn, and Plotly for visualization
Scikit-learn for machine learning models
Statsmodels for statistical analysis

All code will be version-controlled through Git with regular commits documenting the progress.
