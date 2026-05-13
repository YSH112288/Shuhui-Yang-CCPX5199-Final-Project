# Shuhui-Yang-CCPX5199-Final-Project
# Social Anxiety Analysis

## Project Overview

This project looks at factors that are associated with anxiety levels in a social anxiety dataset. The main goal is to understand which personal, lifestyle, and health-related variables seem most connected to higher or lower anxiety scores.

The outcome variable is anxiety level, measured on a 1 to 10 scale. The dataset also includes age, gender, occupation, sleep, physical activity, caffeine intake, alcohol use, smoking, stress level, heart rate, breathing rate, sweating, dizziness, medication, therapy sessions, recent major life events, diet quality, and family history of anxiety.

## Instructions on how to run this code

Please unzip the dataset, import all the required packages, and run the code in order.

## Dependencies or packages needed

- python 3.9.12
- numpy 1.24.3
- pandas 2.3.3
- matplotlib 3.9.4
- scipy 1.7.3
- statsmodels 0.13.2
- scikit-learn 1.1.3
- seaborn 0.13.2

## Main Question

The main research question is whether certain factors are associated with social anxiety. The analysis begins with occupation, then moves into a broader model that includes many possible predictors, and finally looks more closely at stress and sleep together.

## Data Exploration

The first part of the code explores the dataset through summary plots. This helps show the spread of each variable and gives a quick sense of how the data are distributed before running statistical tests.

The dataset has 11,000 observations and no missing values in the version used for this analysis.

## Occupation And Anxiety

The analysis first compares average anxiety levels across occupations. The average anxiety scores are fairly close across groups. Teachers have the lowest average anxiety level at about 3.75, while lawyers have the highest average anxiety level at about 4.21.

<img width="434" height="278" alt="Screenshot 2026-05-12 at 9 20 35 PM" src="https://github.com/user-attachments/assets/1874d508-6453-49c2-819b-a9d95c12a6dc" />

A one-way ANOVA test shows that anxiety levels do differ significantly across occupations. The p-value is much smaller than 0.05, which means at least one occupation group has a different average anxiety level.

<img width="592" height="30" alt="Screenshot 2026-05-12 at 9 23 45 PM" src="https://github.com/user-attachments/assets/4af883c0-7388-4517-8f63-d007eb6994c5" />

Therefore, I ran a Tukey post hoc test, which shows that the largest difference is between lawyers and teachers. The difference is about 0.46 points on a 1 to 10 anxiety scale. Even though this difference is statistically significant, it is still small in practical terms. This suggests that occupation is related to anxiety, but it does not seem to be one of the strongest factors.

<img width="500" height="31" alt="Screenshot 2026-05-12 at 9 25 24 PM" src="https://github.com/user-attachments/assets/1677c03a-f724-4b7b-872c-ea6c14bc7b3c" />

## Regression Analysis

After looking at the occupation, the code uses multiple linear regression to study all variables together. Categorical variables are converted into numeric columns so they can be included in the model.

The model has an R-squared value of about 0.72, which means the model explains about 72 percent of the variation in anxiety levels. The adjusted R-squared value is very close to the regular R-squared value, which suggests that the model fit is not mainly caused by adding many extra predictors.

The RMSE is about 1.12, which means the model predictions are usually off by a little over 1 point on the 1 to 10 anxiety scale.

<img width="268" height="62" alt="Screenshot 2026-05-12 at 9 29 00 PM" src="https://github.com/user-attachments/assets/144f7049-16d7-4d09-9925-a11a6658fd01" />

<img width="393" height="280" alt="Screenshot 2026-05-12 at 9 33 57 PM" src="https://github.com/user-attachments/assets/365beb8f-2fc1-4894-8428-c526bdf95237" />

Because the variables are measured in different units, standardized coefficients are used to compare the strength of predictors more fairly. Results show that stress level has the strongest positive association with anxiety, and sleep duration has the strongest negative association with anxiety. In other words, higher stress is linked with higher anxiety, while more sleep is linked with lower anxiety.

<img width="558" height="276" alt="Screenshot 2026-05-12 at 9 31 04 PM" src="https://github.com/user-attachments/assets/d7d64c34-11b1-4ca0-9124-4753c9a9fb50" />

Other factors such as therapy sessions, caffeine intake, physical activity, age, and diet quality also show relationships with anxiety, but stress and sleep stand out the most.

## Stress And Sleep

The final part of the analysis looks more closely at stress and sleep. Both variables are grouped into low, mid, and high categories.

A two-way ANOVA shows that stress level has a significant relationship with anxiety. Sleep level also has a significant relationship with anxiety. The interaction between stress and sleep is significant as well.

<img width="636" height="89" alt="Screenshot 2026-05-12 at 9 59 21 PM" src="https://github.com/user-attachments/assets/571f3fe0-5ddf-4ce7-94a2-92d1b19b546a" />

This means the relationship between stress and anxiety changes depending on sleep level. When stress is low, sleep level does not make as large a difference. When stress is high, people with less sleep tend to have much higher anxiety than people with more sleep.

<img width="378" height="275" alt="Screenshot 2026-05-12 at 9 37 16 PM" src="https://github.com/user-attachments/assets/1d458fb1-36a1-4cdf-8e3f-50ac84e31b7b" />

This supports the idea that sleep may help buffer the relationship between stress and anxiety.

## Main Findings

- Stress level is the strongest positive predictor of anxiety in this analysis.

- Sleep duration is the strongest negative predictor of anxiety.

- Occupation differences are statistically significant, but the actual differences between occupation groups are small.

- Stress and sleep work together. Poor sleep appears to matter most when stress levels are high.

- The regression model explains a large amount of variation in anxiety levels, but the results should be understood as associations, not proof that one factor directly causes anxiety.

## Conclusion

The analysis suggests that anxiety is more strongly connected to stress, sleep, and lifestyle or health-related factors than to occupation alone. Occupation shows some differences, but those differences are small compared with the patterns seen for stress and sleep. The strongest takeaway is that stress is closely linked with higher anxiety, and sleep seems especially important when stress is high.
