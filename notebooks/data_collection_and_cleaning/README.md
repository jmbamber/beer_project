
<b>Data collection and cleaning</b>

Data was scraped from the website [www.beeradvocate.com](http://www.beeradvocate.com), “the go-to website for beer and the benchmark for beer reviews and ratings due to our focus on quality, integrity, and respect”. It has a large database of user created reviews on all kinds of beer that can be imagined. It not only has text reviews with overall scores, but also scores for individual aspects of beer (taste, smell, mouthfeel, etc.).

Since different styles of beer have very different features that make them good (no one wants a flat lager, but an English Bitter on the other hand…), this project was done one style at a time. What follows is using data on American Pale Ales (APAs).

Scraping reviews was a multi-stage process. There are separate pages for each beer type, then for each individual beer. First the top level page of APAs was scraped to get a full list of the beer names and the urls for each of their pages. Then those urls were used to get information on each beer (descriptions, scores, reviews, etc.). There was no need to scrape all reviews of all beers, so a sample of each were scraped.

Some cleaning was done, e.g. if a reviewer had not given individual scores for smell, taste, etc. then the scores were imputed using the overall score of the beer itself (if all scores are given then the overall score is a weighted average of these features), and some bad data was removed. In the end there were 17k reviews of 150 different APAs.

See full details and code here: [APA Scraping and Cleaning](./02_apa_scraping_cleaning.ipynb)
