##### Load libraries #############################

library(rtweet)
library(tidyverse)
library(here)

##### Extract tweets #############################

fed <- search_tweets(
  "federer", n = 18000, include_rts = FALSE, lang = "en")

Sys.time()
# Tweets extracted on "2018-07-12 20:49:05 NZST"
# Within a day of Federer losing to Anderson

serena <- search_tweets(
  "serena williams", n = 18000, include_rts = FALSE, lang = "en")

Sys.time()
# Tweets extracted on "2018-07-12 21:11:29 NZST"
# The day after Serena progressed to the Wimbledon semis

##### Data wrangling #############################

fed <- fed %>%
  select(user_id, status_id, created_at, screen_name, text,
         source, reply_to_status_id, reply_to_user_id,
         reply_to_screen_name, is_quote, favorite_count,
         retweet_count, hashtags, quoted_status_id,
         quoted_text, quoted_created_at, quoted_source,
         quoted_favorite_count, quoted_retweet_count,
         quoted_user_id, quoted_screen_name, protected,
         followers_count, friends_count, statuses_count) %>%
  unnest() %>%
  write_csv(here("fed.csv"))

serena <- serena %>%
  select(user_id, status_id, created_at, screen_name, text,
         source, reply_to_status_id, reply_to_user_id,
         reply_to_screen_name, is_quote, favorite_count,
         retweet_count, hashtags, quoted_status_id,
         quoted_text, quoted_created_at, quoted_source,
         quoted_favorite_count, quoted_retweet_count,
         quoted_user_id, quoted_screen_name, protected,
         followers_count, friends_count, statuses_count) %>%
  unnest() %>%
  write_csv(here("serena.csv"))



# To do in blog post:

# Data preparation
# (remove stop words, fix text encoding, no duplicate tweets)

# n-gram frequency

# Sentiment analysis - single-word sentiment
### bing (positive / negative binary categorisation)
### AFINN (positive to negative, continuous scale)
### nrc (multiple sentiment categories)

# Sentiment analysis - sentence-level
### Useful ref: https://blog.exploratory.io/twitter-sentiment-analysis-scoring-by-sentence-b4d455de3560

# Parts-of-speech extraction
# Bigram networks
### Useful ref: https://www.tidytextmining.com/ngrams.html

# Topic modelling
### Useful ref: https://www.tidytextmining.com/topicmodeling.html