# City Air - Dsa210-project
## Project Overview
This project analyzes the relation between Tuzla’s air quality and my sleep patterns over a duration of three months. By using publicly available air pollution data with my personal sleep data from a mobile app, I aim to explore whether the changes in air quality impacts my sleep duration and quality. From data collection to using data visualization and statistical analysis, I will assess trends and test hypotheses about the topic. I aim to provide personal insights into how environmental factors affect sleep and contribute to a broader understanding of urban health challenges.

## Motivation
From coming from countryside onto living in a metropolitan city like Istanbul, I wondered how enviromental factors like air pollution may be affecting my sleep. By relying on objective, publicly available datasets and my own sleep records from mobile apps, I aim to take a data-driven approach to a key aspect of well-being. The findings could potentially help me optimize my sleep schedule as well as raise awareness on how air pollution is impacting one's well-being.

## Learning Objectives
**1. Analyzing the Relationship Between Sleep & Air Quality:** I will test whether poor air quality is associated with reduced sleep duration or lower sleep quality.

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
Time series plots to track trends in sleep duration vs. air quality.
Scatter plots to explore possible correlations.
Heatmaps to show relationships between multiple variables.

**Hypothesis Testing:**
Sample hypotheses:

H₀: Air quality does not affect sleep duration or quality.
Hₐ: Higher pollution levels correlate with shorter or lower-quality sleep.
Perform statistical tests to validate findings.

**Trend Analysis & Prediction:**
Create a regression model to predict sleep quality based on air pollution levels.
Identify patterns such as seasonal changes in air quality and their impact on sleep.
Example Analysis
For instance, I will compare my average sleep duration on days with “Good” air quality vs. days with “Unhealthy” air quality. I will also create a scatter plot with PM2.5 levels on the x-axis and sleep quality scores on the y-axis to identify potential trends. If a clear negative correlation exists, it would suggest that air pollution might contribute to poorer sleep.

## Data Preparation
Air Quality Data: Daily averages for six pollutants and the U.S. AQI index from IQAir/Istanbul Hava Kalitesi İzleme Merkezi.
Sleep Data: Nightly sleep duration (hours), sleep quality score (0–100), and time-to-sleep (minutes) from a personal app.

No missing values across 35 daily records.

Outliers (identified via the IQR method) found in PM₁₀, O₃, SO₂, sleep quality, and time-to-sleep; each was inspected and removed to prevent distortion.
## Data Analysis
**Descriptive Statistics**

PM₂.₅: Mean = 20.55 µg/m³ (σ = 7.06; 8.7 – 36.1)

CO: Mean = 408.6 µg/m³ (σ = 184; 123 – 886)

Sleep Duration: Mean = 6.90 hr (σ = 0.95; 5.1 – 9.1)

Sleep Quality: Mean = 63.29 (σ = 15.39; 27 – 92)

**Visualizations**

Time Series Overlay: Daily PM₂.₅ vs. sleep quality—revealed occasional inverse patterns but no consistent day-to-day lag.

Correlation Heatmap: Highlighted CO’s negative association with sleep quality (r ≈ –0.51).

Histograms & KDEs: Showed roughly normal sleep-duration distribution and right-skewed pollutant levels.

Seasonal Decomposition (PM₂.₅): Weekly cycles were apparent, with slightly higher mid-week peaks.

**Data Transformation**

Weekend Indicator: Binary flag (is_weekend) from day-of-week.

Sleep Efficiency: sleep_quality / sleep_duration

Latency (hrs): time_to_sleep / 60

Pollution Index: Weighted sum of standardized pollutant z-scores (PM₂.₅ 0.5; PM₁₀ 0.2; O₃ 0.1; NO₂ 0.1; SO₂ 0.05; CO 0.05), providing a single composite measure.

Categorical Bins:

PM₂.₅: Good/Moderate/Unhealthy for Sensitive/Unhealthy

Sleep Quality: Poor/Fair/Good/Excellent

These enrichments will allow me in multi-scale analyses (continuous, categorical, composite indices).

## Hypothesis Testing & Results
Weekend vs. Weekday Sleep Duration

H₀: No difference in mean sleep duration.

T-test result: t = 0.68, p = 0.507 → fail to reject H₀ (no significant weekend effect).

**Correlation Tests:**

CO: r = –0.51, p = 0.002 → significant negative correlation with sleep quality.

Other pollutants & overall index: weak (|r| < 0.33) and non-significant (p > 0.05).

Cluster Analysis (K-Means, k = 3)

Cluster Centers (original units):


Cluster	PM₂.₅	          Sleep Quality	  Sleep Duration

0	      16.54	          55.13	          5.58

1	      27.37	          53.00	          7.24

2	      17.88	          74.44	          7.33

Interpretation:
Cluster 2 (moderate pollution) aligns with the highest sleep quality/duration, hinting at non-linear or threshold relationships.

## Interpretation
Key Finding: Carbon monoxide stands out as the only pollutant with a robust negative impact on sleep quality.

No Evidence: Overall pollution index or weekend/weekdays meaningfully altered sleep duration.

Complex Patterns: Cluster analysis suggests that moderate pollution days may coincide with better sleep—pointing to possible threshold or adaptive effects.


## Machine Learning Tasks
**Prediction Goal:**

My aim is to predict nightly sleep quality (0-100) as a function of temporal and environmental factors. I selected sleep quality as it measures both sleep duration and restfulness quality. Also it gives more of a better resolution than just saying bad and good sleep as well as enable regresssion.

If it is possible to predict nights of poor sleep based on polution, one could schedule solutions for it(sleep masks, earlier sleep etc.).

**Features For Modeling**

**pollution_index:** Sum of weighted pollutant z scores(PM2.5, PM10)

**sleep_efficiency:** Sleep quality per sleep duration

**is_weekend:** Day is weekend or not

**PM2.5_log, PM10_log:** To reduce right skew in pollutants

## Models and Evaluation
**Linear Regression Model:** The baseline model. It assumes linear, additive effects on features. It gives direct interpration for coefficients (how sleep quality changes per PM2.5 µg/m^3)

**Random Regression of Forest:** This model captures non linear interactions and importance of features. It is robust to skewed distributions and outliers.

**Support Vector Regressor:** This model is kernelized method for flexible non linear regression with robust error control.

**Evaluation Metrics:** R² (Coefficient of Determination): A fraction of variance in sleep quality explained by the model. 1 is perfect and 0 is not better than mean.

RMSE (Root Mean Squared Error): The average prediction error in sleep quality. Lower the value better it is and it penalizes large errors

MAE (Mean Absolute Error): The average absolute error. It is easier to interpret as we say "on average it is off by x points".

Also we will also show which feature matters most, checks for patterns and visually assess fit.


## Conclusion
At the end of this project, I hope to answer:

Does air pollution in Istanbul significantly affect sleep duration or quality?

Is there a threshold below which sleep is noticeably affected?

How do weather conditions interact with the effect of air pollution on sleep?

Can a predictive model be built to predict sleep quality based on environmental conditions?

This project will not just provide individual insight into how air quality affects one's health individually but also serve as a real-world application of data science principles, combining personal data with city environmental studies.
