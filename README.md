# Predicting Advertisement Sales w/Machine Learning and Time Series

## Project Overview
___

### Data and Methods
___


### Results
___
The sentiment analysis results show that while both depressed and not depressed both have a relatively similar positive Vader score, those that are indicative of depression have a much stronger negative score and a composite score that is more negative than positive.  
![image](https://raw.githubusercontent.com/camilla-zhang/depressing_tweets/master/figures/sentiment_distribution.png)
The emoji analysis finds that the depressed tweets are more closely associated with the crying face, upside down face, melting face, weary face, and pensive face, whereas the  normal tweets are more closely tied to the blue diamond, fire sign, heart hands, and smiling face with hearts.
![image](https://raw.githubusercontent.com/camilla-zhang/depressing_tweets/master/figures/emojis_bar_graph.png)
The most strongly associated features of depression among Twitter users are related to taking medicine, negative emotions, time words, and certain actions such as work, whereas the least significant features are collectively more miscellaneous.
![image](https://raw.githubusercontent.com/camilla-zhang/depressing_tweets/master/figures/not_depressed_wordcloud.png)
![image](https://raw.githubusercontent.com/camilla-zhang/depressing_tweets/master/figures/depressed_wordcloud.png)
![image](https://raw.githubusercontent.com/camilla-zhang/depressing_tweets/master/figures/features.png)
We also find that the Neural Network, with 3 hidden and 1 dropout layer has the best performance for precision with 91% accuracy, followed by the single hidden layer neural network. 

The results from all models are as follows:

1. Linear Regression: 78.5%
2. Random Forest: 89.7%
3. XG Boost: 92.4%

