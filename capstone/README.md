# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Capstone Project: Netflix Movie Recommender

### Project Overview

The goal of this project is to build a recommender system to help users find movies and shows that fit their preferences and tastes so that they will be more likely to maintain a subscription with Netflix. 

Due to user privacy issues and the unavailability of datasets containing both movie content details and user ratings, we would be using _two_ separate datasets to build _two_ distinct recommender systems - **Content-Based Filtering Model** and **Collaborative Filtering Model**.

This has been a core focus for Netflix in recent years. Based on an academic paper penned by Gomez-Uribe and Netflix's Chief Product Officer Neil Hunt, they assert that ['the combined effect of personalization and recommendations is estimated to save them more than $1 billion per year.'](https://www.businessinsider.sg/netflix-recommendation-engine-worth-1-billion-per-year-2016-6?r=US&IR=T) This would be a significant area of cost savings for the tech giant as it is expected to spend more than [$17 billion on global content](https://variety.com/2020/digital/news/netflix-2020-content-spending-17-billion-1203469237/) for the current financial year.

### Data Set Used

There are two datasets used:

**1. Netflix Movies and TV Shows dataset** -- this dataset consists of tv shows and movies available on Netflix as of 2019. The dataset is collected from Flixable which is a third-party Netflix search engine.

​	The columns of the dataset consists of:

- `show_id` - Unique ID for every Movie / Tv Show

- `typeIdentifier` - A Movie or TV Show

- `title` - Title of the Movie / Tv Show

- `director` - Director of the Movie

- `cast` - Actors involved in the movie / show

- `country` - Country where the movie / show was produced

- `date_added` - Date it was added on Netflix

- `release_year` - Actual Release year of the move / show

- `rating` - TV Rating of the movie / show

- `duration` - Total Duration - in minutes or number of seasons

- `listed_in` - Genre

- `description` - The summary description

  

**2. Netflix Prize dataset** -- this movie ratings dataset was released by Netflix in October 2006 as a Kaggle challenge to improve on its own recommendation system _Cinematic_. Prizes were awarded if a team could improve the accuracy score by a certain threshold. 

Netflix provided over 100 million ratings (and their dates) from over 480 thousand randomly-chosen, anonymous subscribers on nearly 18 thousand movie titles. The data were collected between October, 1998 and December, 2005 and reflect the distribution of all ratings received by Netflix during this period. The ratings are on a scale from 1 to 5 (integral) stars.

​	The columns of the _training_ dataset consists of `CustomerID`, `Rating`, `Date`

- MovieIDs range from 1 to 17770 sequentially.

- CustomerIDs range from 1 to 2649429, with gaps. There are 480189 users.

- Ratings are on a five star (integral) scale from 1 to 5.

- Dates have the format YYYY-MM-DD.

  The columns of the _movie_titles_ dataset consists of `MovieID`, `YearOfRelease`, `Title`

- MovieID do not correspond to actual Netflix movie ids or IMDB movie ids.

- YearOfRelease can range from 1890 to 2005 and may correspond to the release of
  corresponding DVD, not necessarily its theaterical release.

- Title is the Netflix movie title and may not correspond to 
  titles used on other sites. Titles are in English.

## **Data Cleaning**

- The _Netflix Movies and TV Shows dataset_ consists of null values in multiple columns - 1,969 in *director* column, 570 in *cast* column, 476 in *country* column, 11 in *date_added* column and 10 in *rating* column. This could be due to the unavailability of the data on Flixable the third-party Netflix search engine.
- The _Netflix Prize dataset_ consists of null values in the ratings column for - 4,499 in _combined_data_1.txt_ 
- As there are no reasonable approaches in imputing the null values using inferences, we will drop the null values from the columns for this project.

## **Content Based Filtering Model**

This type of recommender uses the description of the item to recommend next most similar item. It uses the product features or keywords used in description to find the similarity between the items.

We cannot compute the similarity between the given description in the form it is in our dataset. For this purpose, TF-IDF is calculated for all the documents which would simply return you a matrix with each word representing a column. TFIDF Vectorizer would do this for us in a couple of lines.

We did the Cosine Similarity, Euclidean Distance and PearsonR correlation to measure how similar the documents are irrespective of their size.

## **Collaborative Filtering Model**

Collaborative filtering for recommender systems based on the similarity between items calculated using people's ratings of those items.

#### To implement item-based collaborative filtering:

To implement an item based collaborative filtering, KNN is a perfect go-to model and also a very good baseline for recommender system development. KNN is a non-parametric, lazy learning method. It uses a database in which the data points are separated into several clusters to make inference for new samples.

KNN does not make any assumptions on the underlying data distribution but it relies on item feature similarity. When KNN makes inference about a movie, KNN will calculate the “distance” between the target movie and every other movie in its database, then it ranks its distances and returns the top K nearest neighbor movies as the most similar movie recommendations.

## Contact

**Team Lead (Contact) : [Samuel Cheong](https://github.com/samcheongjy)(@SamuelCheong)**



