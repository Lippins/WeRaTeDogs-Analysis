# WeRateDogs Twitter Archive Data Analysis
## Overview
This project aims to wrangle, analyze and visualize the tweet archive of Twitter user [@dog_rates](https://twitter.com/dog_rates), also known as WeRateDogs. We Rate Dogs is a Twitter account that does exactly what it says. It rates dogs, while providing funny and interesting captions. 

This project comprises three central aspects:

- Data gathering to collect relevant data on tweeted dogs, their breed, and user interactions in form of retweets and likes.
- Thorough data cleaning, to prepare it for analysis.
- Analysis and visualization of insights from the cleaned data.

## Wrangling the Dataset
### Gathering Data
The data used for analysis was gathered from three different sources:
- [The Enhanced Twitter archive data](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59a4e958_twitter-archive-enhanced/twitter-archive-enhanced.csv), compiled by [@dogrates](https://twitter.com/dog_rates) and shared with Udacity. This archive contains basic tweet data for all 5000+ of their tweets, as at August 2017. Udacity provided this file, so it was treated as file on hand.
- An [Image predictions tsv file](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv), compiled by running every image in the WeRateDogs Twitter archive through a neural network that can classify breeds of dogs. The file was downloaded programmatically from Udacity servers, using the [requests](https://pypi.org/project/requests/) library.
- Additional data for each tweet in the archive (retweet count, favorite count, and hashtags) was pulled from the twitter API using the Tweepy library.
### Assessing Data
The assessment process identified both quality and tidiness issues across the data collected. A summary of the findings during data assessment can be found in the `wrangle_report.pdf` file.
### Cleaning Data
Each piece of gathered data was cleaned for the quality and tidiness issues identified during assessment. Cleaning involved removing duplicate records, converting datatypes, removing redundant columns, and ensuring that the struture of each dataset conformed to tidy data practices. A summary of the entire cleaning process can also be found in the `wrangle_report.pdf` file.

Cleaned copies of all dataframes were merged into a master dataframe, then stored into `twitter_archive_master.csv`. The master data comprises 1961 rows and 12 columns.

## Analysis Focus
The analysis process was directed at exploring the following:
- The most popular dog breeds tweeted by WeRateDogs.
- The highest rated breeds on average.
- Activity on the WeRateDogs twitter account within the time period.
- User engagement, as it relates to posts created on the account.
- How users interact with tweets that relate to various dog stages.
- Hashtags and how they relate to user engagement.
- The association, if any, between retweets and likes.
- Most favoured dogs, from each dog stage.

User engagement was assessed in terms of retweets and likes.

## Findings and Conclusion
After exploring and building visualizations form the data. The following insights were gleaned:

- In terms of popularity, the top 5 breeds are the Golden Retriever, Labrador retriever, Pembroke, Chihuahua, and the Pug.
- The Majority of the popular breeds also enjoyed high ratings. In fact, Popular breeds constitute 13 of the 20 most rated dogs.
- Puppos (the equivalent of teenage dogs) are people favorites. Their posts gather the highest likes and ratings on average.
- Doggos (the equivalent of adult dogs) are the most retweeted dogs.
Hashtags are not really common place on WeRateDogs. Only about 1.2% of the total tweets had hashtags included.
- Where hashtags were used, the #WomensMarch protest and #ScienceMarch rally gathered the most engagements: Some dogs participated in these events.
- WeRateDogs original tweets have been declining in number. However, user interactions have been growing.
- Retweets and likes are strongly correlated, with a positive correlation coefficient of 0.93. This relationship is even more visible on a log scale.

An article created from the insights above can be found in the `act_report.pdf` file.

## Python Libraries Used
- [Numpy](https://numpy.org)
- [Pandas](https://pandas.pydata.org)
- [Requests](https://pypi.org/project/requests/)
- [os](https://docs.python.org/3/library/os.html)
- [Tweepy](https://www.tweepy.org)
- [Json](https://docs.python.org/3/library/json.html)
- [Pillow](https://pillow.readthedocs.io/en/stable/)
- [Plotly](https://plotly.com/python/)