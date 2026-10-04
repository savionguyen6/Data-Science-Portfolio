## Project 2 — Is it Possible to Predict North Carolina's Housing Market?

---

## What's the Problem

 From the beginning, when the world formed, the first creature that was not a single-celled organism roamed the sea. Living in its world, its home, some find it or even have to make it, and that idea has not changed for land-bound creatures as well. Finding shelter from the elements, from prey, from any danger that surrounds them. A home is a place many desire to have. From the first man who crafted his home from mud and sticks when he thought a cave or under a tree was not enough, to building structures of mass with stone in the ancient world, and now to the modern era of concrete, metal, and more. But none came free; none came without waste or trade, and so a deal had to be made. 

 The homes we live in, newly built or not, passed down from the past generation or not, all came at a cost, and it was either the ones before us or we who had to pay the price, but price is not something that has a limit to it. It changes, and change is caused by a great many reasons. The reasons for change can be measured; they can be assumed, or even made up to create an illusion that makes it easier to understand a change. Now, in this project, it will answer whether machine learning can help address a problem, but not really a problem, but more of an inquiry. “How will housing market prices in North Carolina change in the next year?” Who would not want to know how much housing costs? When to buy, when to sell. Helping buyers and realtors make decisions on the value of a home- not the memories, but the money.

 This project will specifically look at the housing market in North Carolina and will use variables such as active listings, building permits, homes sold, housing units, median household income, mortgage rate, new listings, and population. All these variables will help determine/predict the Zillow Home Value Index (ZHVI) of North Carolina in 2025. 

---

## Data Description

 The data used in this project come from several reliable sources, including the U.S. Census Bureau, Zillow, Freddie Mac, and the U.S. Bureau of Labor Statistics. These sources collect data that can help explain changes in the housing market. The U.S. Census Bureau provides information such as population, number of housing units, and median household income. The Census Bureau also provides building permit data, which shows the number of new homes that are approved to be built. Zillow provides housing price data that can be used to see how home prices have changed over time. Freddie Mac provides mortgage rate data, which can help show how borrowing costs can affect housing prices. The Bureau of Labor Statistics provides unemployment data that can also help explain changes in the economy and housing market.

 These variables provide important information that can be used to answer the research question, “How will the housing market in North Carolina change in the next year?” By looking at past housing prices and other factors such as population, income, housing units, and mortgage rates, the project can find patterns that may help predict future housing prices. However, there are some weaknesses in the data. Housing prices can be affected by many things that are not included in the project, such as changes in the economy, interest rates, and buyer behavior. Because of this, the model can only provide an estimate of what may happen to the housing market and cannot guarantee what will happen.

---

## Data Cleaning and Preparation

 When it came to starting this project, I was gonna need many variables, and handling them was a task. Collecting them was a task, but in the end I had them; it came down to how to proceed. Most of the data was downloaded as a CSV, meaning I could look at each CSV file and see what was missing, what was matched, what was not, and what was useful to help further this project along. Before discussing the next step, I should say that the sources of these datasets are potentially trustworthy sources of information; no one can say 100% that something is credible, but it is reasonable to trust that these organizations that provided such data are trustworthy sources of information to be used.  

 When it came to cleaning the data, it was only a bit of a nuisance because the 2020 data conflicted with the data, as many things caused problems due to the lack of data. COVID was a problem, leaving many missed and uncollected data. So, in relation to this project, 2020 data had to be omitted from the final dataset that would be created with all necessary data from all variables and from the time period they are from.

 With that information handled, moving on to each dataset. Each collected source contained a full set for the United States, so there would be no need to collect only North Carolina data to help answer the research question. After collecting each variable within each dataset for a specific, tailored time period, which was from 2005 to 2024, excluding 2020, I could finally create a whole dataset for this project with its specific features.

 However, it was not done because, looking at the CSV files, there was one that did not hold data going back as far as 2005, but only to 2019. So, a decision had to be made. Omit this CSV file with its variables because it did not have data starting from 2005, or only use data from all files starting from 2019. I chose to keep the file, include it in the final dataset, and start from 2019. The decision came from the thought that modern data would be more effective than stretching back to historical data, because looking at the closer economic standing with the present would provide a more accurate prediction.

---

## Findings

## Correlation Heatmap & OLS
![OLS model](../graphs/OLS.png)
![Correlation Heatmap](../graphs/recent_correlation_heatmap.png)

 The OLS model using 2019–2024 data explained 98.3% of the variation in North Carolina ZHVI (R-squared = 0.983). Population, housing units, median household income, building permits, and new listings were statistically significant predictors at the 5% level or below. Mortgage Rate, Homes Sold, and Active Listings were not significant, as they were above the 5% level. The correlation heatmap provides additional context by showing the relationships between ZHVI and the recent market variables, as well as the relationships among the predictors themselves. The strong correlations shown in the heatmap help explain the high overall R-squared of the OLS model, while correlations among the predictor variables may also contribute to differences between the simple relationships shown in the heatmap and the individual OLS coefficients. Although the OLS model has a very high R-squared, the low Durbin-Watson statistic (0.642) indicates positive autocorrelation in the residuals, which is important because the data are monthly time series, and so the data will follow closely with their closer relationships.

## Scatter Regression Trend
![ZHVI regression relationships](../graphs/ZHVI_regression_relationships.png)

 What can be said is that each scatter plot shows the relationship between each variable and the target variable, ZHVI. These graphs show that as North Carolina has grown, housing prices have also gone up. Population, housing units, and household income all move upward with housing prices, while things like homes sold, new listings, and active listings move downward. This shows that even though there are changes in the housing market, the price of homes has continued to rise.

## Market Trends
![recent market trends 2019 onward](../graphs/recent_market_trends_2019_onward.png)

 These graphs show how much the North Carolina housing market has changed from 2019 to 2025. The population, number of housing units, and household income have all increased, while homes sold and the number of homes available have generally gone down. At the same time, housing prices continued to rise, showing that homes have become more expensive even while some parts of the housing market have slowed down or taken dips.

## Training and Testing

 Two models, linear regression and random forest, were used to answer this question about the housing market. The random forest model was created to look at the housing data from multiple different options instead of relying on one pattern. It uses 300 decision trees to look for patterns in the data, while limiting it to five levels of how complicated each tree can become so that the model does not just memorize what happened in the training data. The Linear Regression model was created to find the relationship between the housing information and future housing prices. Instead of looking at many different decision paths like the random forest, linear regression looks at how the variables move together and uses those relationships to estimate the next year's housing price.

During the training phase, all collected variables were used, along with additional information that can help explain changes in housing prices. When it comes to buying and selling in economic terms, you can’t just look at numbers, but shifts—shifts in the year, the season, and what happened before. Housing prices are not just affected or mainly decided by median household income, building permits, or mortgage rates. Like how certain products can cost different prices during different times of the year, the same can be true for houses. Because of this, the training included information from the same month of the previous year, since what happened before can give an idea of where prices may move in the future. The time of year was also considered because the housing market does not always behave the same way throughout the year. The models were trained using information from 2019, 2021, 2022, and 2023, while 2024 was kept separate for testing to see whether the patterns learned from the past could help predict housing prices for 2025.

 The results show that both models were able to learn the patterns found in the housing market during the training period. The Random Forest performed slightly better than the Linear Regression model, with an R-squared of 0.998 compared to 0.994, meaning both models were able to explain almost all of the variation in the training data. The models were also compared using RMSE and MAE, which help show how far the predictions were from the actual housing prices. MAE represents the average size of the model's mistakes, while RMSE also measures the size of the mistakes but gives more weight to larger errors. The Random Forest had an MAE of about $1,087 and an RMSE of about $2,099, compared to Linear Regression's MAE of about $2,686 and RMSE of about $3,533. This shows that the Random Forest made smaller mistakes during training and was able to follow the patterns in the training data more closely.

 Linear Regression predicted that housing prices would continue increasing throughout 2025, reaching around $363,000–$367,000, while Random Forest predicted a much lower path, beginning around $334,000 and falling to around $317,000 by December. This difference shows why the testing stage is important. Both models learned from the past, but don’t tell or predict the same story. This means the model that performs best on the training data is not truly the model that will make the best prediction, for you will only know which is best when compared with real, actual true data. And now, the actual 2025 housing prices can be used to see which model's story is closer to what really happened.

## Actual VS Prediction
![2025 actual vs predicted ZHVI](../graphs/2025_actual_vs_predicted_ZHVI.png)

![model prediction error comparison](../graphs/model_prediction_error_comparison.png)

Finally, the end result of comparing how well both models' predictions did against the actual 2025 values is an interesting find. Looking at the results, there are differences and similarities that can be seen. First, the differences. Linear Regression had a much worse prediction, overshooting the actual housing prices with an RMSE of $28,935, a MAE of $28,797, and an R-squared of -458.44. Its predictions were consistently higher than the actual values, showing a much more expensive or increasing housing market than what actually happened. Looking at the Random Forest prediction, it followed the actual values much more closely compared to Linear Regression, but eventually fell short later in the year, showing a lower or decreasing housing market price. Its RMSE was $9,244, its MAE was $6,660, and its R-squared was -45.90. In comparison, these results were much better than Linear Regression; however, the Random Forest still struggled to predict the actual 2025 values accurately.

Both models also fell short of the baseline that was created to give a standard for the models to reach or improve upon. The baseline had an RMSE of $3,570, a MAE of $3,050, and an R-squared of -5.99. Since lower RMSE and MAE values mean smaller prediction errors, the baseline performed better than both models. The Random Forest came closer to the baseline than Linear Regression, but neither model was able to outperform it.

Another difference: looking closer, there is quite a strange occurrence when comparing the actual values to the predicted values. In some months, when the actual housing price increased, the predicted price moved in the opposite direction, and when the actual price decreased, the prediction sometimes increased. This shows that the models were not always able to follow the month-to-month changes that occurred in the actual 2025 housing market.

Another important finding can be seen when comparing the training results to the testing results. During training, both models performed extremely well, with the Random Forest having an R-squared of 0.998 and the Linear Regression having an R-squared of 0.994. However, when the models were tested against the actual 2025 values, both R-squared values became negative. This shows that performing well on the patterns from previous years did not replicate or showcase promising performance for predicting a new year. The models were able to learn the historical housing data very well, but the actual 2025 market did not follow those patterns closely enough for either model to make highly accurate predictions.

Even though the Random Forest did not outperform the baseline, it was still the stronger model when compared directly to Linear Regression. Its MAE was about $6,660 compared to Linear Regression's $28,797, meaning the Random Forest's predictions were much closer to the actual housing prices on average. This shows that the Random Forest was able to learn some of the patterns in the housing market better than Linear Regression, even though those patterns were not strong enough to predict the entire 2025 market accurately.

Overall, these results show that predicting housing prices is much more difficult than simply looking at patterns from previous years. The models were able to learn the historical housing data very well to a point, but the actual 2025 market proved otherwise. This suggests that changes in the housing market can occur in ways that historical data alone can not give context to.

## Finale

During this project, by studying and understanding the results that I was given, I can firmly answer my research question, “How will housing market prices in North Carolina change in the next year?” I don't know; the machine learning does not know, and the person or thing that knows what will happen is a higher power. You can predict numbers and values, but how close can you get? This project was to see if machine learning was advanced enough to determine the future values of a market that is based on multiple factors. Factors can be measured, but some influences are simply out of human control until they happen and become reasons for a change in value.

You cannot predict the housing market on the basis of several reasons. First, you cannot predict the exact future, because it has not happened yet. Many could argue that you can predict the future, but tell that to a person who studies statistics and logic, and they would probably tell you otherwise. The models can learn from what happened in the past, but that does not mean the future will follow the same path. This was shown when both models performed extremely well during training but struggled when they were tested against the actual 2025 housing prices.

Second, there are factors such as human evaluation that influence a house's value, and that comes from different influences itself, as there are basic biases and uncontrollable circumstances. A house is not just a number in a dataset. Its value can be influenced by its location, condition, neighborhood, people's opinions, economic changes, and what buyers are willing to pay at a certain point in time. Some of these things can be measured, while others are difficult to put into a dataset and predict.

Third, the results showed that having more complicated machine learning does not automatically mean having a better prediction. The Random Forest performed better than Linear Regression when compared to the actual 2025 values, but neither model was able to outperform the baseline. This means that even though the models were able to find strong patterns in the historical data, those patterns were not enough to predict what happened in 2025 accurately. The housing market did not follow the exact story that the models learned from the past.

To conclude, the answer to the research question is not that North Carolina housing prices will definitely increase or decrease by a certain amount. Instead, this project showed that housing prices can be estimated using historical information, economic variables, previous housing prices, and seasonal patterns, but there is a limit to how accurately the future can be predicted. Machine learning can give us an educated prediction based on what has already happened, but it cannot account for every change that has yet to happen. The future housing market is not created by numbers alone. It is also influenced by people, decisions, economic changes, and circumstances that a model cannot know until they occur.

## Limitations and Reflection

After completing this project, there is room for improvement. This project could have been improved, but there are limitations to what can be added, measured, and reasoned about. A home's value is determined by a great many reasons: the area that surrounds the home, the schooling, the transportation, the crime rate, the size of the house, the land it is set upon, the history of the home (haunted, murders, etc.), the state of the house; even the way a house is designed and built can make it a different cost. Houses can also influence the value of the other houses around them. There are so many reasons that a housing market cannot be predicted, and that is only including housing-related reasons.

Housing prices are also related to economic shifts, inflation, tariffs, recessions, new policies, interest rates, and so much more. To include everything that is possibly related to the housing market for even a single state is hard to predict; try scaling that to the whole country, and it would become even more difficult to measure. Numbers can tell us what has happened and can help us find patterns, but numbers alone do not cause or determine what will happen next.

There can also be biases within the data that can influence the results. The Zillow ZHVI is an estimate of housing values rather than the exact selling price of every home, meaning the models are learning from Zillow's way of estimating the market. Another bias comes from using statewide data. North Carolina has many different housing markets, and a home in Charlotte can have a completely different value and set of influences compared to a home in a rural or coastal area. By combining all of these areas together, some of those differences can become hidden within the statewide numbers.

There are also factors that were not included in the data, such as crime, school quality, transportation, the condition of a home, the neighborhood, and the location of the property. If these factors influence what people are willing to pay, but the model cannot see them, then the model is only working with part of the picture. Another bias comes from the fact that the models learn from the past. If the housing market changes in a way that did not happen in the training data, the models may continue following old patterns even when those patterns no longer fit. This could be one reason why the models performed so well during training but struggled when predicting the actual 2025 housing market.

There are also improvements that could have been made to the data used in this project. More years of data could have been included, along with more variables that could help explain why housing prices change. Variables such as crime rates, school quality, location, property size, home age, unemployment, inflation, construction costs, and other economic factors could give the models more information to work with. However, adding more variables does not automatically mean the prediction will become correct. More information can help explain the past, but it still cannot account for every event that could affect the future.

Looking back on the project, the biggest limitation is not that there were not enough variables, but that there are too many things that can influence a housing market. A house is given a value by people, and those people make decisions based on things that cannot always be measured. Machine learning can find patterns in the numbers, but the numbers are still only a representation of what happened. They cannot completely explain why someone decides that one house is worth more than another or why an entire market suddenly changes. There is room for improvement in this project, but there is also a limit to how much information can be collected and used before it becomes too big or broad to predict. 

## Code

## References

U.S. Census Bureau. (n.d.). American Community Survey data via API. U.S. Department of Commerce. Retrieved September 29, 2026. Census ACS API

U.S. Census Bureau. (n.d.). Building Permits Survey. U.S. Department of Commerce. Retrieved September 29, 2026. Census Building Permits Survey

Zillow Economic Research. (n.d.). Housing data. Zillow. Retrieved September 29, 2026. Zillow housing data 

Freddie Mac. (n.d.). 30-year fixed rate mortgage average in the United States [MORTGAGE30US]. FRED, Federal Reserve Bank of St. Louis. Retrieved September 29, 2026. FRED MORTGAGE30US series 

U.S. Bureau of Labor Statistics. (n.d.). Local Area Unemployment Statistics. U.S. Department of Labor. Retrieved September 29, 2026. BLS Local Area Unemployment Statistics 

Redfin. (n.d.). Redfin Data Center. Retrieved September 29, 2026. Redfin Data Center 

AI DISCLAIMER: ChatGPT and Google's AI assistant were used to retrieve variables that I struggled to access on my computer, as well as to find information on linear regression and random forest trees (No prior knowledge/very little). They were also used to help troubleshoot problems, as well as to provide details that could be added to help with visuals, data cleaning, etc. 

