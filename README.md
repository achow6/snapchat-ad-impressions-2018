# Looking at How Different Independent Variables Can Help Predict the Number of Impressions for an Advertisement

This project serves to see whether independent variables, such as targetting a specific audience, spending, and number of days an ad is shown, can be used to predict the number of impressions for an advertisement. [Advertising is important](https://www.bizfilings.com/toolkit/research-topics/marketing/advertising-pr/effective-advertising-makes-people-remember-your-name) because it increases the public's awareness, recognition, and preference of you and your brand. For political ads, a successful advertising campaign [could be the difference](https://www.npr.org/sections/itsallpolitics/2012/10/26/163652827/nine-states-near-unlimited-cash-a-flurry-of-ads) between winning or losing a bill or election. Being able to predict the number of impressions is important and helpful for businesses, politicians, and advocacy groups to decide how to maximize their advertisement outreach with the money they have available.

This project uses Snapchat political and advocacy advertisement data. In view of the aforementioned information, this project serves to determine whether targetting an ad to a female audience, number of days an advertisement is shown, and amount spent on an advertisement can be used to predict impressions for an advertisement.

# Business Question
Can you predict the number of impressions for a United States advertisement for any of the years of given data?

# Data Question
Simple Linear Regression: Can amount money spent on an advertisement predict the number of impressions for it?

Multiple Linear Regression: Does targetting the ad to a specific audience (female), number of days an advertisement is shown, and amount spent on an advertisement predict the number of impressions?

# Data Source
**Snapchat**: This is a social media platform primarily used for messaging. The app uses political and advocacy advertisements, which is explored in this project. This project looks at the publically available advertisement data from 2018 from Snapchat's [Snap Political Ads Library](https://www.snap.com/en-US/political-ads/).

# Data Analysis
Once the original data were downloaded, the data were filtered to advertisements in the United States paid in USD to keep location and currency consistent. Most advertisements in the data were United States ads, and very few United States ads were paid in other currencies, so this filtering did not have a large impact on the results. 
"StartDate" and "EndDate" (containing date and time) columns were split into separate columns for date and time. Some end date cells were empty after splitting the column because the advertisement ended on the same day, so IF statements were used to fill these with the start date value. IF statements were also used to numerate the "Gender" column (male=0, female=1, all genders=2).
A scatterplot chart with a linear trendline was created to compare the "Spend" and "Impressions" columns. The data analysis tool was used to summarize the output of the simple linear regression comparing these two columns.
The data analysis tool was used again to summarize the output of the multiple linear regression comparing "Spend", "Days", and "Gender" columns against "Impressions". "Gender" was found to be statistically insignificant, so the data analysis tool was used again to summarize the relationship between "Spend", "Days", and "Impressions".

# Data Answer
![alt text](https://github.com/achow6/snapchat_ad_impressions_2019/blob/master/Picture1.png)

Here we see that amount spent in USD and number of advertisement impressions is positively correlated. This visual suggests that the more money is spent on an advertisement, the more impressions it will receive.

![alt text](https://github.com/achow6/snapchat_ad_impressions_2019/blob/master/SLR.png)

This is the summary output for the simple linear regression model showing the relationship between spending and number of impressions. The equation indicated by this summary is: Impressions = 19253.83559 + 269.0282066(Spend). This suggests, like the visual, that as spending increases, so does impressions. 
The p-value for "Spend" is 6.2144E-148. Since this is less than 0.05, it indicates that amount of money spent is statistically significant in predicting number of impressions. The F Significance is the probability that none of variables matter for end model, so a lower value is better. For this regression model, the F significance is 6.2144E-148, which shows that the variable "Spend" matters for the end model. The R squared value is 0.741776725, which indicates the percentage (about 74.2%) of data that can be predicted with the equation.

![alt text](https://github.com/achow6/snapchat-ad-impressions-2018/blob/master/MLR.png)

This is the summary output for the multiple linear regression model showing the relationship between spending, number of days an advertisement was shown, whether the ad targetted a female audience, and number of impressions. The equation indicated by this summary is: Impressions = -144,142.43 + 345.366247(Spend) + 4,927.7299(Days) + 132,310.767(Female Aud?). This suggests that as spending and length of time an advertisement is shown increases and the ad becomes more targetted to a female audience, impressions increase.
The  independent variables "Spend" (p-value 9.893E-141), "Days" (p-value 8.65409E-07), and "Female Aud?" (p-value 6.89504E-05) were statistically significant for predicting impressions because their p-values were lower than 0.05. The regression model for "Spend", "Days", "Female Aud?" and "Impressions" has a low F significance (3.7436E-147) like the simple linear regression model, which shows that "Spend", "Days", and "Female Aud?" matter for the end model. The R squared value is 0.646415085, which indicates that about 64.6% of the data can be predicted with the model.

# Business Answer
These models suggest a positive relationship between spending, days an advertisement is shown, whether the ad is targetted to a female audience, and number of impressions. Increasing amount spent, number of days advertising, and targetting specific audiences could lead to increased impressions. Using these models, businesses can explore how to use their advertising resources more efficiently. In view of the findings in this analysis, political advertisements should target specific advertisements to populations that find that information most relevant (i.e. target female audiences regarding pro- or anti-abortion advertisements). Political advertisements should also increase spending and amount of time their advertisement is available to the public to maximize impressions.

Further research that sees how male-targetted advertisements, data on other advertisements (i.e. merchandise, food), and data from other advertising platforms could be useful for predicting impressions. For political ads specifically, further research could look at how number of impressions affect voter turnout and election results.
