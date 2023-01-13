# How News affects stock prices
--- 

> ## Problem Statement 

In the past, we've observed stock market share prices shift in minutes, hours, and days. The most obvious cause for a stock's price to rise or fall is due to supply and demand. When more investors want to acquire the stock, the demand exceeds the supply, causing the price to rise; conversely, when more investors sell the shares (high supply less demand), the price falls.
However, there are a number of factors that influence the demand and supply of any share prices. Among the causes are:
1. Political stability and economic trends
2. Conflicts such as war
3. Natural calamity
4. Firm performance, financial position, earnings, new products and services.
5. Fundamental and technical analysis.
6. Social media press releases or fake news

These and other elements are the factors that influence stock sentiment.
The goal of this study is to determine which social media misleading news causes share prices to rise or fall. One of the motivations for spreading fake news is to make money by selling when the stock market is rising and buying when it is falling. This causes investors to make poor judgments, putting their investments at risk. In this study, machine learning algorithms will be utilized to analyze false news as example with start with Apple stock historical datasets from January 1, 2021 to June 31, 2022, as well as their tweets during the same period of time.

It was observed in the past that the sudden changes of the share price by fake news would not stay for long time. Perhaps the market would self-correct right away with the help of big sectors and professional investors likely recognize the fake news and drive the stock back to normal. This will help to detect and determine which tweets are fake news or not using a sentiment score

> ## Datasets used
---

Tweeter 
– Tweets for most known stock 
Finnhub 
– Stock news 
GoogleNews
- News articles 
Kaggle
– News and opinion articles: 221513 072012 - 012020

- Yahoo finance allow to download historical data from the following link:
> **Stock Prices: (01-01-2021 to 06-30-2022)**
- [Apple:](https://finance.yahoo.com/quote/AAPL/history?p=AAPL)
- [Google:](https://finance.yahoo.com/quote/GOOG?p=GOOG&.tsrc=fin-srch)
- [JPM:](https://finance.yahoo.com/quote/JPM/?p=JPM) 
Tweets: Using python library, imported tweets for the above three stocks for the same period of time. 

> ## Exploratory data analysis:
---

For this EDA, the clean-up process was relatively minimal compared to other projects. The only clean-up process required was to reduce the number of features that were deemed less important. Before using Natural Language Processing to analyze the article datasets, we first had to select a particular stock for our modeling. As an example, I chose the AAPL ticker and performed an analysis on it.

[Link](./images/aapl_daily_articles.png)

It is evident that a large number of articles are published daily about Apple. To limit the amount of irrelevant information, I have attempted to view and delete duplicate articles that have been cleaned and organized. It appears that the number of articles written per day is affected by certain events, such as earnings day, new product announcement, or financial report date. This suggests that the number of articles is seasonal in nature.

[Link](./images/aapl_article_writter.png)

Zacks Investment Research Inc. has been found to be the most popular writer of articles for Apple. Zacks is a leading investment research firm that specializes in stock research, analysis, and recommendations. It is likely that they use advanced data science techniques to inform their investment research and provide the best advice to their clients.

Natural Language Processing (NLP) is a powerful tool used for sentiment analysis, which involves classifying emotions or behavior through natural language processing. The process of NLP involves feature extraction, tokenization, lemmatization, and stopword removal. These processes are carried out using machine learning algorithms, which allow for the analysis of complex language data. Through this process, NLP can be used to accurately identify and classify emotions or behavior in natural language data.

> ## Model
--- 

To predict stock prices, four different models were used: Linear Regression, GRU (Gated Recurrent Unit), LSTM (Long Short-Term Memory), and RNN (Recursive Neural Network). In order to find the best parameters, a Python function was written to test a list of different parameters and return the best one. The historical stock price dataset was joined with the news sentiment score dataset, then manually split into train/test datasets, and put through StandardScaler for scaling. Data was processed with a function that took a list of parameters and fitted them to a given model. In the end, the best parameters were determined and a plot of Actual vs Predicted was generated.

[Link](./images/aapl_actual_predicted_plot.png)

#### Parameters performed best outputs:

[Link](./images/final_output.png)

> ## Conclusion

In this project, we were able to predict future stock-closing price using sentiment score and opening stock price. We tested four different models, and the Recurrent Neural Network (RNN) model came out as the best. We used sentiment score from daily news as the baseline input for the GRU model, but the mean square error was often high. To improve the accuracy of the prediction, we added more input features to the model.

It is recommended to test the following steps in order to improve the effectiveness of stock price prediction. 
* An additional filter should be applied to news articles and tweets. This filter should be created with custom stopwords, which will help to distinguish the words that have an impact on the sentiment score from those that do not. 
* The most popular news providers, social media platforms, and posts used by investors for their investment decisions should be identified. 
* Lastly, more modeling techniques such as ARIMA, SARIMA, and SARIMAX should be added to the analysis. By implementing these steps, the accuracy of stock price prediction can be improved.


> ## Refrences
---
- [What are the key factors cause market go and down](https://www.investopedia.com/ask/answers/100314/what-are-key-factors-cause-market-go-and-down.asp)
- [How to download historical stock prices in python.](https://www.geeksforgeeks.org/how-to-download-historical-stock-prices-in-python/)
- [Media bias fact check Methodology](https://mediabiasfactcheck.com/methodology/)
- [Sentiment analysis opinion mining with python nlp](https://pub.towardsai.net/sentiment-analysis-opinion-mining-with-python-nlp-tutorial-d1f173ca4e3c)
- [The 20 US banks at the top in social media](https://thefinancialbrand.com/news/social-media-banking/the-20-u-s-banks-at-the-top-in-social-media-154682/)
- [https://www.tandfonline.com/doi/full/10.1080/08839514.2022.2151159]
- [https://www.diva-portal.org/smash/get/diva2:1584099/FULLTEXT01.pdf]
- [https://www.blueskycapitalmanagement.com/machine-learning-in-finance-why-you-should-not-use-lstms-to-predict-the-stock-market/]