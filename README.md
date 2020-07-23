# Disaster Tweets NLP Project

## Purpose

The purpose of this project was to explore NLP concepts and apply them to a data set. The data was found on
a [kaggle](https://www.kaggle.com/c/nlp-getting-started) competition and the goal of the project was to analyse the tweets to classify the topic,
i.e whether the tweet was about a natural disaster or not. I trained a multinomial Naive Bayes model that had an accuracy of 0.80.

## Data

The data came in csv files and was already split into a training and testing set. The training set had 7613 entries, while the test
set contained just under half this number of entries. The columns consisted of an id, a keyword, a location and the text from the tweet.

## Process

### EDA

Firstly, I analysed the words that each tweet contained by looking at the most used words in each topic category. This gave me an
interesting insight into what language twitter users used to discuss disasters. I found that tweets about disasters didn't use the same 
words as much as other tweets and the most commonly used words seemed to be locations or words that could be used to describe the disaster.

<img src='images/token_frequencies.png'/>

Then I looked into the words that had the largest difference in frequency between the two categories of tweets.

<img src='images/token_frequency_differences.png' />

I thought these words would probably provide the biggest source of variance between the two topics and so be most useful to the Naive Bayes model.

I then calculated some meta data about the tweets:

- Word Count
- Stopword Count
- Average Word Length
- Character Count
- Punctuation Count
- Unique Word Count
- Number/Figure Count

These statistics provided a small amount of variance between the two topic categories, I decided to use these variables in my machine learning model.

### Cleaning

- Lowercasing - to normalise the case of the words.
- Removing URLs.
- Removing punctuation - to isolate words.
- Removing stopwords - to reduce dimensionality by removing commonly used words in the English language.
- Stemming - to attempt to standardise words by removing the endings of related words.

### Modelling

I then used a bag of words with unigrams and bigrams and a Multinomial Naive Bayes model to predict the topic of the tweet. The model had an
accuracy of 0.80 on the test set.
