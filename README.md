# Analysis of fake news sites and viral posts, 2016 - 2018

This repository contains data and analysis supporting the BuzzFeed News article, [In Spite Of Its Efforts, Facebook Is Still The Home Of Hugely Viral Fake News](https://www.buzzfeednews.com/article/craigsilverman/facebook-fake-news-hits-2018) published December 28, 2018. Please read that article, which contains important context and methodological details, before proceding.

## Data

Over the past four years, BuzzFeed News has maintained lists of sites that publish completely fabricated stories. As we encounter new ones and debunk their content, we add them to the list. To produce this story, we used this list as well as some sites brought to our attention by fact-checking website, [Lead Stories](https://leadstories.com/).

The `data/sites_2016.csv`, `data/sites_2017.csv`, and `data/sites_2018.csv` files contain lists of fake-news domains we included in our analyses for each of those years. 

The `data/top_2018.csv` file contains information about the top fake news articles of 2018 (by Facebook engagement) published by our 2018 list of fake news sites. It contains the following columns:

- `title`: The title of the article.
- `url`: The URL of the article.
- `fb_engagement`: The number of Facebook engagements the article received. (See note below.)
- `published_date`: The date the article was published.
- `category`: The article's main theme, as categorized by BuzzFeed News. Category may be `Crime`, `Politics`, `Medical`, `Music`, `Sports`, `Business`, or uncategorized.
- `source`: The data source, if other than BuzzSumo. (See note below.)

Some of these data were used in BuzzFeed News' [2017 analysis of fake news](https://github.com/BuzzFeedNews/2017-12-fake-news-top-50).

## Note on Facebook engagement data

Most of the engagement data comes from [BuzzSumo](https://buzzsumo.com/).

Nine stories were not picked up by our BuzzSumo search, but were brought to our attention by our contacts at [Trendolizer](http://www.trendolizer.com/). In seven of those stories, Trendolizer used the [Facebook Graph API](https://developers.facebook.com/docs/graph-api/) to retrieve engagement counts.

For the remaining two stories, the domain had been blocked by Facebook's servers, but only after the stories had gone viral and generated large engagement counts. For these URLs, BuzzSumo and the Facebook API both innacurately returned 0 engagement counts. Trendolizer archived the data before Facebook blocked the domain, and so we used their counts.

Trendolizer retrieves Facebook engagement data by scraping the displayed number on the "like" button of a Facebook post. Because the like button rounds down large numbers for display, these data are are slight undercounts.

## Analysis

The analysis is contained in `notebooks/analysis.ipynb`. The code there, written in Python, compares the 2018 site list to its 2017 and 2016 counterparts. It also looks for trends over time and calculates the most popular domains and categories.

## Licensing

All code in this repository is available under the [MIT](https://opensource.org/licenses/MIT) License. The data files in the `data/` directory are available under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0) license.

## Feedback/Questions

Contact Scott Pham at scott.pham@buzzfeed.com.

Looking for more from BuzzFeed News? [Click here](https://github.com/BuzzFeedNews/everything) for a list of our open-sourced projects, data, and code.
