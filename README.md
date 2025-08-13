# IBM Applied Data Science Capstone Project

Presentation slides: [See Capstone_Presentation.pdf](https://github.com/akariri79/IBM-Applied-Data-Science-Capstone-Project/blob/main/Applied%20Data%20Science%20Capstone%20Presentation.pdf) for a visual summary of this work.

## 📌 Executive Summary

This capstone project focuses on predicting whether the SpaceX Falcon 9 first stage will land successfully using a range of machine learning classification techniques. The workflow consisted of:

- Data acquisition, cleaning, and structuring

- Exploratory data analysis (EDA)

- Interactive visual analytics

- Model building and evaluation

Findings from the analysis indicate that certain launch characteristics are strongly correlated with mission outcomes. Among the tested algorithms, Decision Trees achieved the highest predictive performance for this task.

## 📖 Introduction

The goal of this project is to forecast the landing success of Falcon 9’s first stage. SpaceX advertises launch costs of approximately $62 million—significantly lower than competitors charging $165 million or more—due largely to its ability to reuse first stages. Being able to predict landing success has direct cost implications and could aid competitors or clients in bid decision-making.

Many failed landings are intentional, such as controlled ocean landings. This project examines whether variables like payload mass, orbit type, and launch site can accurately predict the likelihood of a successful landing.

## 🛠 Methodology Overview and 📈 Results
### 1. Data Collection

  - Two approaches were used:

  1. [SpaceX API](https://github.com/akariri79/IBM-Applied-Data-Science-Capstone-Project/blob/main/jupyter-labs-spacex-data-collection-api-v2.ipynb)

      Libraries: requests, pandas, numpy, datetime

      Queried Falcon 9-specific launches, transformed JSON to DataFrame, and handled missing data using column means.

      Final dataset: 90 records × 17 features.

  2. [Web Scraping](https://github.com/akariri79/IBM-Applied-Data-Science-Capstone-Project/blob/main/jupyter-labs-webscraping.ipynb)

      Libraries: requests, BeautifulSoup, pandas, re, unicodedata

      Scraped Wikipedia launch tables for Falcon 9, extracting headers and row data.

      Final dataset: 121 records × 11 features.

### 2. Exploratory Data Analysis

  [Pandas & NumPy](https://github.com/akariri79/IBM-Applied-Data-Science-Capstone-Project/blob/main/labs-jupyter-spacex-Data%20wrangling-v2.ipynb)

  - Counted launches per site, orbit frequency, and mission outcomes.

  [SQL](https://github.com/akariri79/IBM-Applied-Data-Science-Capstone-Project/blob/main/jupyter-labs-eda-sql-coursera_sqllite.ipynb)

  - Environment: IBM DB2

  - Queried aggregated stats (e.g., average payloads, site counts) using SQL functions such as SUM, AVG, and COUNT.

### 3. Data Visualization

  [Matplotlib & Seaborn](https://github.com/akariri79/IBM-Applied-Data-Science-Capstone-Project/blob/main/jupyter-labs-eda-dataviz-v2.ipynb)

  - Scatterplots, bar charts, and line plots to explore feature relationships (e.g., payload mass vs. site success rate).

  [Folium](https://github.com/akariri79/IBM-Applied-Data-Science-Capstone-Project/blob/main/lab-jupyter-launch-site-location-v2.ipynb)
 
  - Mapped launch sites, marking successful vs. failed missions and showing distances to nearby infrastructure.

  [Dash & Plotly](https://github.com/akariri79/IBM-Applied-Data-Science-Capstone-Project/blob/main/spacex-dash-app.py)

  - Built interactive dashboard with dropdowns and sliders to explore launch site performance and payload-success relationships.

### 4. Machine Learning Modeling

  [Machine Learning Model](https://github.com/akariri79/IBM-Applied-Data-Science-Capstone-Project/blob/main/SpaceX-Machine-Learning-Prediction-Part-5-v1.ipynb)

  - Libraries: pandas, numpy, matplotlib, seaborn, scikit-learn
  
  - Models: Logistic Regression, SVM, Decision Tree, KNN
  
  - Steps: Data scaling, train-test split, model fitting, hyperparameter tuning (GridSearchCV), and evaluation (accuracy, confusion matrix).

  Performance ranking based on GridSearchCV best scores:
  
   - Decision Tree — 0.8750 ✅
    
   - KNN — 0.8482
    
   - SVM — 0.8482
    
   - Logistic Regression — 0.8464

## 🧠 Key Insights

  * Features such as payload mass and orbit type significantly influence mission outcome.
  
  * Heavy payloads tend to have higher success rates for orbits like Polar, LEO, and ISS, but not GTO.
  
  * Decision Trees provided the most reliable predictions in this dataset.

## 🏁 Conclusion

This project demonstrates that machine learning can be applied to historical Falcon 9 launch data to predict landing success. The Decision Tree model achieved the best performance and can serve as a practical baseline for future refinements.

Created: August 2025
