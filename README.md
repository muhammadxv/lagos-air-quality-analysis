# Air Quality Analysis in Lagos, Nigeria

This project explores **PM2.5 air quality levels in Lagos** using open data from Sensor.Africa  
covering **November 2023 to April 2025**. The analysis focuses on understanding pollution patterns,  
detecting anomalies, and visualizing daily, weekly, and monthly air quality trends.

## Objectives
- Clean and merge monthly air sensor data for Lagos.
- Visualize PM2.5 behavior over time.
- Identify outliers and pollution exceedances.
- Analyze temporal patterns using daily, weekly, and monthly averages.

## Data Source
Data obtained from **Sensor.Africa** public air quality archives:
https://open.africa/en/dataset/sensorsafrica-airquality-archive-lagos
## Dataset
18 Months data from **Sensor.Africa** structured and uploaded on my Kaggle:
https://www.kaggle.com/datasets/aminumuhammad/sensors-africa-air-quality-archive-lagos

## Methods Used
- Data cleaning and preprocessing with pandas.
- Outlier detection and removal.
- Visualization using matplotlib and seaborn.
- Time-series resampling and rolling averages.

## Results Summary
- PM2.5 levels in Lagos show irregular fluctuations with no smooth long-term trend.
- Some short-term pollution spikes observed, possibly due to weather or traffic variations.
- The 30-day rolling average indicates inconsistent but occasionally elevated pollution periods.

## 🗂️ Folder Structure

lagos-air-quality-analysis/
│
├── lagos_air_quality.ipynb # Jupyter notebook with all code
├── data/ # cleaned datasets
└── README.md


## Next Steps
- Incorporate PM10 and temperature/humidity variables.
- Build predictive models for short-term PM2.5 forecasting.
- Develop an interactive dashboard to monitor air quality in real-time.

---
**Author:** [Aminu Muhammad]  
**Tools:** Python, pandas, matplotlib, seaborn, scikit-learn

