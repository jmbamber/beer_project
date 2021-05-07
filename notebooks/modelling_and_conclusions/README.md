
<b>Modelling</b>

Positive and Negative reviews were defined as being above and below the median score given by reviews. This ensured an even split of classes to predict, making the modelling simpler.

The NLP technique chosen was a straightforward “bag of words” approach using a TF-IDF vectoriser, and the model used was a logistic regression. In both cases a simpler approach that results in an easy to interpret and human-readable outputs were the most important consideration. This is because the final output of this project is not the model itself, but the features that go into making it.

While a more complex model like a Random Forest may result in a more accurate model, Logistic Regression is ideal here. A Logistic Regression tells us not only how important a given feature was in the prediction, but also whether it was pushing the prediction towards positive or negative. A Random Forest can only give a total importance.

After some optimisation, the final Logistic Regression model run on test data had an accuracy of 0.77 (precision and recall were both in line with accuracy), well above the baseline of 0.50 and more than good enough to begin to draw some conclusions.

For full detail of modelling and code used, see here: [APA Modelling](./02_apa_beer_modelling_draft.ipynb)

---
<b>Conclusions</b>
  
By extracting the coefficients used by the model we can identify the most important features for predicting if a review is positive or negative.

As might be expected though there are a lot of inherently positive and negative words that turn up in the most important features (e.g. “fantastic”, “delicious”, “bad”, “disappointing”, etc.). Recommending a brewer make a “delicious” beer isn’t exactly the most groundbreaking insight, so these worlds were removed.

The top coefficients for (positive and negative) for APAs were these:

 <img src=../../images/APA_coefficients.jpeg>
  
Based on the model, the key to making a well-liked APA is to make it fruity, especially tropical fruits, while avoiding making it bland or too much like a lager.

---
<b>Next Steps</b>

The first, and most obvious step to take would be to take the code written here and use it to create models/recommendations for a wide variety of different beer styles. Unfortunately, after running this project on two styles of beer (APAs and English Bitters) the Beer Advocate website was updated to require a log-in to get more than one page of reviews per beer. As such the scraping part is now much more difficult and would require a new process to be created. If that was done, the modelling section should remain useful.

Another avenue to pursue could be to create more granular models based on the individual ratings of the beers (taste, smell, etc.). This may help create more specific insights for a brewer looking to improve a specific aspect of their beer.

Finally, to test the validity of the model created here, it could be tested using the brewers’ descriptions of their beers to see if it was still accurate at predicting scores. This would be like an even more extreme version of a test-train split, to see how the model performs on a completely new (but still related) dataset. NOTE: This was done, see below!

---

<b>Bonus - Extra Model Validation</b>

For fun, and to really test the validity of my model, I decided to try using it on the brewers’ descriptions of their own beers to predict the score of the beer itself.

If the conclusions above are accurate, we would expect that an APA that has the key recommended features would be more positively reviewed than one without those features. The easiest way to see if a beer is meant to have a specific feature is by using the brewers descriptions.

As before, the beers were split into “good” and “bad” depending on whether their average rating was above or below the median rating of all beers in that style. The model was then tested using the brewers’ descriptions as the features.

The resulting accuracy was 0.61, above the baseline of 0.5, but not as strong as before. This is to be expected though considering it is being tested on completely different data than which it was trained on.

In fact the accuracy is mostly let down by a poor performance on predicting the “bad” beers - the recall of “good” beers was 0.93! Again, this is likely to be expected considering no brewer is likely to use the “negative” coefficients when describing their beer (“grainy”, “bland”, etc.), but they would use the “positive” ones (“tropical”, “juicy”, etc.).

Overall, although the accuracy is only just above baseline, the fact that it is above baseline suggests to me that this model is valid, as it still holds predictive power better than guessing even when used in a different situation than which it was trained.
