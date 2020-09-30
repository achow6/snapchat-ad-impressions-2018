# Looking at How Different Independent Variables Can Help Predict the Number of Impressions for an Advertisement

This project serves to see whether independent variables can be used to predict the number of impressions for an advertisement. Being able to predict the number of impressions is important and helpful for businesses to decide how to maximize their advertisement outreach with the money they have available.
This project uses Snapchat political and advocacy advertisement data. As a Snapchat user who views these advertisements, this information is relevant and interesting to me.
Gender of the targetted audience, number of days an advertisement is shown, and amount spent on an advertisement are the independent variables explored to help predit impressions for an advertisement.

# Business Question
Can you predict the number of impressions for a United States advertisement for any of the years of given data?

# Data Question
Simple Linear Regression: Can amount money spent on an advertisement predict the number of impressions for it?

Multiple Linear Regression: Does gender of the targetted audience, number of days an advertisement is shown, and amount spent on an advertisement predict the number of impressions?

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

![alt text](https://github.com/achow6/snapchat_ad_impressions_2019/blob/master/MLR.png)

This is the summary output for the multiple linear regression model showing the relationship between spending, number of days an advertisement was shown, and number of impressions. The equation indicated by this summary is: Impressions = -95256.86775 + 341.1214575(Spend) + 6403.996258(Days). This suggests that as spending and length of time an advertisement is shown increases, so does impressions.
Notice that gender of the intended audience was not included because it was found to be not statistically significant for the end model (p-value was 0.494253038, which is higher than 0.05). The other independent variables "Spend" (p-value 3.6903E-137) and "Days" (p-value 1.27866E-11) were statistically significant for predicting impressions because their p-values were lower than 0.05. The regression model for "Spend", "Days", and "Impressions" had a low F significance (3.7938E-145) like the simple linear regression model, which shows that "Spend" and "Days" matter for the end model. The R squared value is 0.637740258, which indicates that about 63.7% of the data can be predicted with the model.

These models suggest a correlation between spending, days an advertisement is shown, and number of impressions. Increasing amount spent and number of days advertising could lead to increased impressions. However, gender of the targetted audience does not have a statistically significant effect on impressions and the results suggest that it should not be used to predict impressions. Using these models, businesses can explore how to maximize their advertisement impressions with less money.
