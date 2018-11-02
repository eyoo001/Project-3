# Introduction

With this project, I am attempting to create a model that can accurately predict a post between two subreddits - r/news and r/upliftingnews. In addition, I am also using these subreddits to train against for a model that can perform sentiment analysis. It is my initial assumption that the posts in r/news will be primarily negative, while r/upliftingnews will be majority positive - this should allow for a clear distinction for the models.


## Question

The question I would like to explore is "Does r/news contribute to the societal demoralization and fear-mongering by primarily showcasing negative sentiment articles and headlines?" I plan on utilizing sklearn's classification methods (vectorizers and classifiers - MultinomialNB and Random Forest), as well as NLTK's sentiment analysis library, Vader.

My hypothesis is that r/news will have significantly more negative sentiment in it's distribution, whereas r/upliftingnews will be mostly positive and some neutral. This distinction will lend to a strong model in identifying both subreddit and sentiment.


## Conclusion

After evaluation of the data, I was able to create two models with about 80% accuracy. The predictions yielded the following:

### Sentiment
- 793 predicted negative sentiment (-1), and was negative (-1). True Negative.
- 618 predicted positive sentiment (+1), and was positive (+1). True Positive.
- 104 predicted negative sentiment (-1), but was positive (+1). False Negative.
- 96 predicted positive sentiment (+1), but was negative (-1). False Positive.

### Subreddit
- 538 predicted r/UpliftingNews (-1), and was r/UpliftingNews (-1). True Negative.
- 736 predicted r/News (+1), and was r/News (+1). True Positive.
- 139 predicted r/UpliftingNews (-1), but was r/News (+1). False Negative.
- 208 predicted r/News (+1), but was r/UpliftingNews (-1). False Positive.


The model could predict correctly 80% of the time. This distinction is not as relevant given this dataset, however. From a cursory evaluation, the main reason for these mispredictions can be due to noisy training data. 

Although the models themselves predicted with relative accuracy, my hypothesis was disproven. From the get-go, the distribution of sentiment in the two subreddits were approximately equal; r/news had around an even split between positive and negative sentiment, and r/upliftingnews had a slight higher bias towards positive. This indicated that firstly, it was going to be more difficult than I anticipated to correctly predict both sentiment and subreddit; and secondly, that the sentiment analysis tool was not classifying sentiment very accurately. 


## Next Steps/Improvements

In order to achieve higher accuracy on my models, the first step would be better cleanup of the data to remove excess noise - that includes removing spam, lemmatizing/stemming the words, and perhaps using higher n-grams for contextual analysis. I would also spend more time with the hyperparamters of the models, as well as try boosting. Lastly, I would want to attempt this analysis using the comment data as well, which I did not do this go-around due to an initial low success rate.