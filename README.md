# 💸💰 Exchange Explorer: Predictive Analytics for USD Fluctuations 💰💸
---

## 📈 Table of Contents 📉 <a class="anchor" id="toc"></a>
- [Project Overview](#overview)
    - [Introduction](#intro)
    - [Problem Statement](#problem)
    - [Solution](#solution)
    - [Objectives](#objective)
    - [Potential Impact](#impact)
- [Dataset](#dataset) 
    - [Data Description](#desc)
    - [Data Dictionary](#data-dict)
    - [Data Source](#data-source)
    - [Data Coverage](#data-coverage)
- [Project Roadmap](#roadmap)
    - [Data Cleaning](#cleaning)
    - [Exploratory Data Analysis](#eda)
    - [Feature Engineering](#engine)
    - [Feature Selection](#select)
    - [Model Development](#develop)
    - [Model Evaluation](#eval)
- [Conclusion](#conclusion)
    - [Insights & Findings](#insights)
    - [Key Takeaways](#takeaways)
    - [Future Directions](#nextsteps)
    - [Final Thoughts](#thoughts)

---

## Project Overview <a class="anchor" id="overview"></a>

### Introduction to Exchange Explorer! <a class="anchor" id="intro"></a>
In this project, "Exchange Explorer: Predictive Analytics for USD Fluctuations," we dive into the fascinating world of currency exchange rates, focusing on the US Dollar (USD) — a key player in global finance. The USD's influence stretches far and wide, affecting everything from international trade to personal investment decisions. Our goal is to sift through historical exchange rate data, uncover patterns, and predict future movements using the machine learning techniques.

This isn't just about crunching numbers; it's about providing valuable insights for investors, financial analysts, and policymakers to make informed decisions in a complex market. Through a careful blend of analysis and technology, "Exchange Explorer" aims to shed light on the dynamics of forex markets, making them more understandable and navigable for everyone involved.

### Problem Statement <a class="anchor" id="problem"></a>
The problem we're addressing is the challenge of predicting exchange rates between the US dollar and ten global currencies. Exchange rates are influenced by a complex interplay of economic indicators, geopolitical events, and market sentiment, making accurate predictions difficult. 

This uncertainty poses a significant risk for investors, traders, and businesses involved in international trade. By developing a data-driven approach to forecast these rates, we aim to provide valuable insights that can help stakeholders make informed decisions, and optimize their financial strategies.

### Our Solution  <a class="anchor" id="solution"></a>

Our solution involves using advanced data science techniques to create a predictive model for exchange rates between the US dollar and ten major currencies. We plan to leverage historical exchange rate data to predict future direction of Close rates of USD.

### Objectives <a class="anchor" id="objective"></a>
The main objective is to develop a robust and reliable predictive model for exchange rates between the US dollar and major global currencies. We aim to leverage the power of data science to analyze historical trends, economic indicators, providing accurate forecasts that can inform financial decisions. By achieving this, we hope to reduce the uncertainty and risk associated with currency fluctuations, enabling stakeholders to make more informed and strategic choices in their financial planning and investments. As a first step, the focus will be on analyzing the currency pair CAD=X (which captures the fluctuations of USD to CAD exchange rates).

### Potential Impact <a class="anchor" id="impact"></a>
The potential impact of our solution is significant, as accurate predictions of exchange rates can have far-reaching benefits. For investors and traders, it means better-informed decisions that can lead to increased profits and reduced losses. For businesses engaged in international trade, it can lead to more effective hedging strategies, optimized pricing, and improved financial planning. 

Additionally, policymakers and economists can use these insights to better understand currency market dynamics and make informed decisions. Overall, our solution has the potential to enhance financial stability and efficiency in a globalized economy.

## Dataset <a class="anchor" id="dataset"></a>

### Dataset Description <a class="anchor" id="desc"></a>
This dataset offers a comprehensive view of daily currency exchange rates, from 2008 to 2023. Currency rates can be affected by various factors, including interest rates, inflation, political instability, economic performance, and global market developments. Understanding these rates over time can provide valuable insights into economic trends, market behaviors, and the impacts of global events on currency values.

The currency pairs included in this dataset are:
- USD to INR (INR=X)
- USD to JPY (JPY=X)
- USD to EUR (EUR=X)
- USD to GBP (GBP=X)
- USD to AUD (AUD=X)
- USD to CAD (CAD=X)
- USD to CHF (CHF=X)
- USD to CNY (CNY=X)
- USD to HKD (HKD=X)
- USD to SGD (SGD=X)

### Data Dictionary <a class="anchor" id="data-dict"></a>
|Column|Data Type|Description|Remarks/Examples|
|:---|:---:|:---|:---|
|`Ticker`|`str`|The currency pair being represented.||
|`Date`|`str`|The date in YYYY-MM-DD format.||
|`Open`|`float`|The opening exchange rate of the day.||
|`High`|`float`|The highest exchange rate of the day.||
|`Low`|`float`|The lowest exchange rate of the day.||
|`Close`|`float`|The closing exchange rate of the day.||
|`Adj Close`|`float`|The adjusted closing exchange rate of the day.||
|`Close`|`float`|The volume of the currency traded on that day.||

### Data Source <a class="anchor" id="data-source"></a>
The dataset can be found on Kaggle [Here](https://www.kaggle.com/datasets/pavankrishnanarne/daily-currency-exchange-rates-2008-present)

### Data Coverage <a class="anchor" id="data-coverage"></a>
- Temporal Coverage 
    - Starting Date: 01 Aug 2008
    - Ending Date:  31 Jul 2023

## Project Roadmap / Framework  <a class="anchor" id="roadmap"></a>
- Baseline modeling
- Non-linear modeling
- Advanced modeling

### Data Cleaning / Preprocessing <a class="anchor" id="cleaning"></a>
This step will clean and preprocess the data to handle missing values, outliers, and normalize the data for better model performance. This will be an iterative process through the sprints.

### Exploratory Data Analysis <a class="anchor" id="eda"></a>
- Handling missing values
- Appropriate datatype selection for the columns
- Removing unhelpful columns from the dataset

### Feature Engineering <a class="anchor" id="engine"></a>
Time Series
    - Percent Change - captured percent change between each day's Close rates for trend detection, volatility analysis.
Decision Trees and Random Forest
    - Moving Average - 5-Day, 10-Day and 50-Day Moving Average features were engineered to capture short-term, intermediate-term and long-term trends.

### Feature Selection <a class="anchor" id="select"></a>
Features selected for analysis for respective models:
- Polynomial Regression (baseline model): Target feature was 'Close', rest of the features in the dataset were not considered for analysis.
- Time Series - Again, target variable was 'Close' as it changed over a period of 'Time' (the column set as index for the analysis)
- Decision Trees and Random Forest - Aside from a few engineered features for moving averages, target variable was still 'Close' rates, but 'Open', 'High' and 'Low' features in the original dataset were used for the analysis.

### Model Development <a class="anchor" id="develop"></a>
- Baseline modeling
The first baseline model chosen based on EDA was to conduct polynomial regression of degree 2 and 3.
- Non-linear modeling
For the first non-linear modeling, Time Series analysis was conducted to explore the relationship of the Close rates with Time.
- Advanced modeling
For advanced modeling, Decision Trees and Random Forest models were explored to make predictions.

### Model Evaluation <a class="anchor" id="eval"></a>
|`Models`|`R-Squared`|`RMSE`|
|---|:---:|:---:|:---:|
|`Polynomial Regression: degree 2(Baseline)`|`0.658`|`0.27`|
|`Polynomial Regression: degree 3(Baseline)`|`0.848`|`0.322`|
|`SARIMA (2022)`|`NA`|`0.006`|
|`SARIMA ('2021)`|`NA`|`0.007`|
|`Decision Tree`|`0.95`|`0.0029`|
|`Random Forest`|`0.99`|`0.00016`|

##  Conclusion  <a class="anchor" id="conclusion"></a>
The following sections give a all-round findings and key takeaways of this analysis.

### Insights & Findings <a class="anchor" id="insights"></a>
Upcoming in future sprint

### Key Takeaways <a class="anchor" id="takeaways"></a>
Upcoming in future sprint

### Future Directions <a class="anchor" id="nextsteps"></a>
- To explore other currency pair in the dataset to find patterns and trends to explore similarities or differences
- To explore models used in the industry to gain insight into possible comparison in approach to exchange rate predictions

### Final Thoughts <a class="anchor" id="thoughts"></a>
Upcoming in future sprint