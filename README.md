# Exploratory Data Analysis of Covid-19 on House Price Index Due to possible Impact of Employment
## Varsha Tomar
https://github.com/VTomar88/Covid-19-housing-unemployment.git

### Introduction
The world has shocked with Covid-19 effects with quarantines, lockdowns, shutting of business, and job loss. In this study, I wish to understand if the impact on Housing Price Index during Covid-19 is due to loss in the employment. To perform the data analysis, I obtained three datasets from open-source government agencies, cleaned the data-sets and merge them to a final dataset. Final data set have variables: State, Year, Employed, Unemployed, HPI_SA, HPI_NSA, Total covid cases, and Total covid deaths. This study tries to analyze the US data to understand the volatility in housing price index and employment before and during Covid-19.

### Accessing Datasets
Following three datasets were used to perform the model regression analysis:
#### Dataset 1
Covid cases: https://data.cdc.gov/Case-Surveillance/United-States-COVID-19-Cases-and-Deaths-by-State-o/9mfq-cb36 Centers for Disease Control and Prevention (CDC) has a huge database with latest updates on covid-19 cases. This data set is collection of covid-19 cases, and deaths by US states till October, 2022. There are a total of 15 variables in this data set are: submission_date, state, tot_cases, conf_cases, prob_cases, new_cases, pnew_cases, tot_death, conf_death, prob_death, new_death, pnew_death, created_at, consent_cases, and consent_deaths
#### Dataset 2
Unemployment rate: https://www.ers.usda.gov/data-products/county-level-data-sets/download-data/ The unemployment data is recovered from US Department of Agriculture, Economic research studies, which will provide data on unemployment and median household income for US States and counties for 2000-2021 (last update – 6/3/2022). This data set has a total of 5 variables: FIPS_Code, State, Area Name, Attribute, and Value.
#### Dataset 3
Housing Price: https://www.fhfa.gov/DataTools/Downloads/Pages/House-Price-Index-Datasets.aspx#mpo The dataset for housing price will be collected from Federal Housing Finance agency within year 2020-2022. This data set has a total of 6 variables: state, yr, qtr, index_nsa, index_sa, and Warning

### Steps performed in EDA
Steps performed in EDA

#### Step 1. Accessing, cleaning, and combining datasets.
Three datasets for covid cases, unemployment rates and housing prices were collected from reliable US sources as listed above. Then I cleaned the data sets and Descriptive characteristics like mean, mode, distribution spread, and tails were examined. Using common variables, I combined all three datasets into a single dataset. This final data set was used to perform the analysis.

##### Step 2. Distribution analysis
Histograms, probability mass function (PMF), and cumulative distribution function (CDF) were used to understand the distribution of unemployment rates and housing index. Further, normal probability and log-normal probability functions were implemented.
![image](https://github.com/VTomar88/Covid-19-housing-unemployment/assets/107073327/6b1c065f-8598-4005-b352-2925bf15175f)
![image](https://github.com/VTomar88/Covid-19-housing-unemployment/assets/107073327/ac450359-0df2-4e2c-bee6-42b52c5151b9)
![image](https://github.com/VTomar88/Covid-19-housing-unemployment/assets/107073327/c748ed27-e5fd-4348-84fb-c6b1cd1930a9)

##### Step 3. Scatter plot analysis was performed for different variables in the dataframe.
![image](https://github.com/VTomar88/Covid-19-housing-unemployment/assets/107073327/f7219c73-e7ab-4516-ac2f-915829835f18)

##### Step 4. Covariance, Pearson’s correlation and non-linear relationships with Spearman’s Rank correlation were investigated.
Result:  A strong positive relationship can be seen for employed and unemployed data for both before and during covid-19. Before covid-19, the data is linearly related as Pearson's correlation is better than Spearman's Correlation. On contrary, during covid-19, Spearman's correlation is better than Pearson's correlation.
Causation and Correlation: Though the scatter plot shows there is a possible relation between House Price Index and Employment or Unemployment for both before and during Covid-19, the correlation analysis shows that employment/unemployment are not affecting the change in House Price Index. Therefore, there is an indirect correlation between employment and housing prices.

##### Step 5. Hypothesis testing 
The null hypothesis is that the distribution among employed and housing price index is same, and therefore, they are not connected to each other. If the p-value is less than 0.001 then the distribution is significant. 
Result of hypothesis testing:
1.	The p-value for pre-covid test is below 0.001, the distribution of employed or unemployed is not same as House Price Index (HPI).
2.	The p-value for post-covid test is also below 0.001, the distribution of employed/unemployed with HPI is different.

##### Step 6. Regression analysis
1.	Linear regression analysis: Linear regression for HPI and employment/unemployment data for pre-covid USA shows non-significance, I performed multiple regression. In multiple regression, I choose employment, unemployment, and states as the explanatory variables and HPI as the dependent variable.
2.	Multiple regression:
a.	The multiple regression of dependent variable house price index with explanatory variables - employed and states showed that this model is highly predictive (with coefficient of determination, R2 = 0.993). However, the data is significant for major of the states with p-value < 0.001, except CO, ID, OR, SD, UT, VT are the states that were not showing the relationship significant.
b.	The multiple regression of dependent variable house price index with explanatory variables - unemployed and states showed that this model is highly predictive (with coefficient of determination, R2 = 0.990). Contrary to multiple regression with employed with states, unemployed with states regression showed that only a limited states have significant relation (p-value < 0.001). These states include AZ, CO, CT, DC, DE, FL, ID, LA, MA, MN, MT, ND, OR, SD, UT, WA, and WY dataset are significant.
c.	The multiple regression of dependent variable house price index with explanatory variables - employed and states during Covid-19 showed that this model is predictive (with coefficient of determination, R2 = 0.939). The data is significant for major of the states with p-value < 0.001, except CO, DE, HI, ID, ME, ND, NE, NH, NM, NV, OR, RI, SD, UT, and VT are the states that were not showing the relationship significant.
d.	The multiple regression of dependent variable house price index with explanatory variables - unemployed and states showed that this model is predictive (with coefficient of determination, R2 = 0.939). Contrary to multiple regression with employed with states, unemployed with states regression showed that only a limited states have significant relation (p-value < 0.001). These states include AZ, CA, CO, DC, FL, ID, MT, NY, OR, TX, UT, WA, WY are significant.

##### Step 7. Outcome of EDA

Three data sets were obtained from well-known open sources of US government. First challenge was to clean these three datasets and merge into one single data set. The visualization of data suggests that there is indeed a relation between employment or unemployment before and during covid, where employment was high before pandemic and unemployment was high during pandemic. Similarly, House Pricing Index before and after Covid are significantly related where HPI increased drastically after pandemic.

It was interesting to learn that there is no significant linear relation between employment and HPI. So, it is still unclear that increase in HPI during covid is due to increase in unemployment during this period. The analysis of covariance, Pearson's correlation and Spearman's Rank correlation suggested that there is no direct correlation of HPI with employment and unemployment data. The Ordinary Least Square linear regression suggested the same.

The multiple regression, on contrary, predicts that there are states that hold the relation of employment and HPI significant, and other states doesn’t hold the relation to be true. This suggests that the entire US data on employment have not impacted HPI increase during pandemic but is state specific. Therefore, further data analysis of individual states may show which states have employment-based impact on HPI.


