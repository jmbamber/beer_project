# "I was performing analysis of craft beers <i>before</i> it was cool" - Using NLP to find the best features of various styles of beers

<img src="beers_image.jpeg" width="360" alt="Pictured: What I needed to get through my data cleaning">

Personal project using NLP and predictive models to provide insights into key features of beer

### Executive Summary

With the current popularity of the craft beers, it's difficult for indepdendant breweries to stand out. This project aimed to provide independent breweries with the key features that beer drinkers look for in a good beer, through Natural Language Processing and predictive modelling

Information on various beers, and user reviews of these beers, was scraped from [Beer Advocate](www.beeradvocate.com).

Taking one beer style at a time (e.g. APA) the review texts were used to try and predict whether the review score was high or low (defined as being above or below the median for review scores of that style of beer). These predictions were made through the use of a Tf-idf Vectorizer and a Logistic Regreesion model.

The top coefficents (by absolute values) were then identifed for each beer model, after removing "generic" features like "good", "excellent", "average" etc. Thisi resulted in a list of the key beer features that should be either included or avoided to make a well-received beer.

A final test of validation was run by trying to use the model to predict the average score of each beer using the brewers description. In the case of APA the accuracy of this proved to be high enough above baseline that it indicitively confirms the hypothesis that including these features in a beer results in it being better recieved.
