# tweeting-dogs

The repository summarises the data wrangling steps using datasets derived online and ofline.In this case I gather data from the We Rate Dogs Twitter archive. The WeRate Dogs is a renowned dog rating account that allows users to rate images of dogs with a humorous comment about the dog. The rating is a fraction the denominator is always a 10 while the numerator can be less or more than 10.

# Data Gathering
In this stage, three datasets relating to the WeRateDogs Twitter account were gathered and imported into the Jupyter Notebook. These are;

      1). The  WeRateDogs twitter archive
      2). the Twitter image predictions
      3). tweet_df.  
  
The second dataset ocntianed three predictions on the type of dog identified from the images collected from the  prediction dataset. This dataset was downloaded using the requests library and stored as a TSV file. The last dataset,tweet_df, contained additional information on the Twitter archive.. This data was queried from Twitter using the Tweepy API.

# Data Quality and Tidiness Assessment
The  three datasets were assessed visually and programmatically in the jupyter notebook to ascertain their quality and tidiness. The following is a list of the data quality issues identified in the three datasets using the two techniques:

  ## Data Quality issues
  
    • Missing variables in the twitter dataset such as in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status timestamp,and in the master dataset.
    • The rating_denominator is redundant because it has only one unique value,10.
    • Errors in the extraction of ratings_numerator.
    • Presence of retweets in the Twitter data.
    • Incorrect data types; for example, tweet_id is an integer in all the datasets.
    • Tweet_id duplicated in all the datasets.
    • Non descriptive column names e.g p1,p1,p3.

 ## Data Tidiness issues
 
    • The tidiness issue observed from the dataset was that the dog stages were divided into three columns when they should have been in one column. 
    • Three tables contain similar information.

# Data Cleaning
## Data Quality

    • All rows that are retweets(nulls in the retweeted_status_timestamp column were dropped.
    • All columns conisdered redundant and not useful for final analysis were dropped.
    • The extraction of rating _numerators  from the twitter_archive was redone suing Regex and then converted to floats.
    • Incorrect data types were corrected.

## Data Tidiness
    • The three datasets were merged based on the tweet_id.
    • The columns on the dog classes were summarised into one by extracting the class from the columns.


# Data Analysis
Anlysis was conducted to determine:

     • The top rated image/tweet
     • Dominant dog types/breeds in the dataset

