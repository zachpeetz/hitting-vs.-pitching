# A case study in MLB: Does a Team's Hitting or Pitching Indicate More Success?
### Overview
This project investigates the impact of a Major League Baseball team’s offensive and pitching statistics on its overall success, specifically focusing on whether hitting or pitching is a more significant predictor of a team’s win percentage. The analysis includes various statistical methods, including correlation analysis, feature importance evaluation, and machine learning techniques like Random Forest regression, to identify and quantify the impact of offensive and pitching metrics.

### Project Workflow
##### Data Exploration & Cleaning:

The data was loaded from an MLB dataset using Fangraphs, which is a popular site for baseball related statistics. The dataset I used includes various statistics that help measure batting and pitching performance, so I decided to see what matters more to winning?
Missing data was handled by using IterativeImputer, which iteratively estimates and imputes missing values based on other available data.

##### Why I picked FIP and wOBA as the statistics to do this study on

I selected FIP and wOBA because they provide more accurate insights into pitching and batting performance than traditional metrics. They are both considered to be advanced metrics.

FIP:
FIP stands for "Fielder Indpendent Pitching", it ultimately measures a pitcher’s true ability—strikeouts, walks, and home runs—removing the influence of defense. It offers a clearer picture of pitching performance, relying solely on the pitcher's performance and taking their defense out of the equation.

wOBA:
wOBA stands for "weighted on-base average" and it combines multiple offensive stats (e.g., walks, singles, home runs) into a single metric. This statistic also gives more weight to events that are more impactful for scoring runs. 

##### Visual Analysis:

Histograms & Q-Q Plots were created for key independent variables (wOBA and FIP) to assess their distribution and normality.
A correlation matrix was calculated to examine the relationships between variables, specifically focusing on how offensive and pitching stats correlate with the team's win percentage.

##### Feature Scaling:

Given the different ranges of the independent variables, all relevant features were standardized using the StandardScaler to ensure that all data is on the same scale and to improve the performance of the machine learning model.
Machine Learning Model:

A Random Forest Regressor was employed to model the relationship between team statistics and win percentage. Multiple values for the number of estimators were tested to identify the optimal model configuration.
The model’s performance was evaluated using R-squared and Root Mean Squared Error (RMSE). The model achieved an R-squared of 0.658 and an RMSE of 0.044, suggesting a good fit for the data.

##### Feature Importance:

After fitting the model, the feature importances were analyzed to determine which statistics (wOBA vs. FIP) were most influential in predicting a team’s success.
The results showed that wOBA (offensive metric) was slightly more important (0.553) than FIP (pitching metric, 0.447), indicating that offensive performance historically has a stronger impact on a team’s success than pitching performance.

##### Results:

The analysis concluded that, historically, a team’s offense (represented by wOBA) tends to be a slightly better predictor of success (winning percentage) than pitching (represented by FIP).
However, both offense and pitching are crucial factors, and the relative importance of these components can vary depending on the context, such as the team's overall strategy and individual player performance.

##### Key Findings
wOBA (Offensive Metric) had an importance score of 0.553, while FIP (Pitching Metric) had a slightly lower score of 0.447.
Offense has a slightly greater impact on a team's success, though both factors are significant.
Random Forest Regressor showed good predictive power, with an R-squared of 0.658 and RMSE of 0.044.
Feature importance analysis confirmed that offensive metrics are slightly more predictive of a team’s win percentage than pitching metrics.

##### Conclusion
This analysis suggests that hitting (offensive performance) is historically a slightly better predictor of success in Major League Baseball than pitching. While both offense and pitching are essential, teams that perform better offensively tend to win more games. However, this relationship could vary over time and between teams, depending on multiple factors like team strategy and player performance.

##### Visuals

- The changes in each stat per decade  
![image](https://github.com/user-attachments/assets/3ee01254-08b5-4176-8b99-b9d779f08070)

- Comparing the stats to their respective median based upon win percentage  
![image](https://github.com/user-attachments/assets/bb8298af-c8e6-4804-a479-e1976f6b8ef4)

- Visualization of the feature importance scores for wOBA and FIP  
![image](https://github.com/user-attachments/assets/d0c56e93-5626-4b0e-b5d6-be134cd191b1)



##### Tools & Libraries
- Python 3.11
- pandas for data manipulation
- numpy for numerical operations
- matplotlib & seaborn for data visualization
- scikit-learn for machine learning (Random Forest, regression)
- statsmodels for statistical analysis
- IterativeImputer for handling missing data
##### Potential Future Work/Thigns to Add
- Incorporate additional metrics to enhance the model, like defense, ballpark factors, etc.
- Experiment with other machine learning models to compare performance
- Analyze the impact of external factors (e.g., home/away games, team payroll) on success
