# "I was performing analysis of craft beers before it was cool" — Using NLP to find the best features of various styles of beers

<img src=images/beers_image.jpeg width=360 alt="What I needed to get through this project">

Personal project using NLP and predictive models to provide insights into key features of beer

### Executive Summary

With the current popularity of the craft beers, it's difficult for independent breweries to stand out. This project aimed to provide independent breweries with the key features that beer drinkers look for in a good beer, through Natural Language Processing and predictive modeling

Information on various beers, and user reviews of these beers, was scraped from [Beer Advocate](www.beeradvocate.com).

Taking one beer style at a time (e.g. APA) the review texts were used to try and predict whether the review score was high or low (defined as being above or below the median for review scores of that style of beer). These predictions were made through the use of a Tf-idf Vectorizer and a Logistic Regression model.

The top coefficients (by absolute values) were then identified for each beer model, after removing "generic" features like "good", "excellent", "average" etc. This resulted in a list of the key beer features that should be either included or avoided making a well-received beer.

A final test of validation was run by trying to use the model to predict the average score of each beer using the brewers' descriptions. In the case of APA the accuracy of this proved to be high enough above baseline that it indicatively confirms the hypothesis that including these features in a beer results in it being better received.

---

Below are links to the stages of the project. The stages below use data on American Pale Ales (APAs), chosen because they were the most popular beers to have been reviewed at the time of scraping, so they provided the most robust dataset.

<b>Aims</b>

While predictive models are most commonly used to, well, predict things, there are other uses for them.

The goal of this project was to use a predictive model, trained on the text of beer reviews, to accurately predict whether the review was ultimately positive or negative. The use of this is not the predictive nature of the model itself however. By creating an accurate model, and identifying the features (i.e. the words of the review) that are strong predictors, we can identify which real-world features are most likely to make a beer well liked (or not).

E.g. if the word “hoppy” is a very strong predictor of a review being positive, we can assume that a beer in that style is more likely to be positively reviewed if it is hoppy.

[Data Collection and Cleaning](/notebooks/data_collection_and_cleaning)

[Modelling and Conclusions](/notebooks/modelling_and_conclusions)
