# Recommendation System

Generally speaking, three methods are widely adopted in building up recommendation system, and they are often combined due to the attributes of each method.

- Popularity-based recommendation
- Content-based recommendation
- Collaborative-filtering recommendation

For TMDB dataset, we will mainly use Popularity-based and Content-based methods. We will do Collaborative-filtering with Steam gaming dataset.

Besides the application of each method in recommendation system, pros and cons are discussed in the notebook.

## 1. Popularity-based & Content-based Recommendation

This project works on [TMDB data](https://www.kaggle.com/tmdb/tmdb-movie-metadata) to build up a movie recommendation system.

Due to the lack of user-product pair preferences, I used popularity-based recommendation and content-based recommendation only.

Click to review [the notebook.](https://github.com/melodydadada/Recommendation-System/blob/master/TMDB%20movie%20rating.ipynb) OR see [Kaggle kernel](https://www.kaggle.com/chenma/recommendation-system-with-tmdb-movie-data) directly

## 2. Colaborative-Filtering Method
**A Recommendation System with Surprise!**

### 2.1 [Colab Link](https://colab.research.google.com/drive/1xBFFFeDAoFtzvPUE3HG9ctWVO980frIc)
### 2.2 Objective
In this report, we aim to analyze steam data with userID, games they played, and number of hours they spent on each game.
We used two methods to establish a collaborative filtering recommendation system:
- User-based Collaborative Filtering
- Item-based Collaborative Filtering

### 2.3 Exploratory Data Analysis
There are 11350 unique userID and 3600 unique itemID. There is no rating data, but we can use number of hours user play the game as a measure of preference, which is the case of **implicit recommendation**.
User rating for a game is denoted as the log transform of number of playing hours in order to scale the number.

### 2.4 Modeling
1. User-based Collaborative Filtering
User-based Collaborative Filtering uses user ratings as the attributes of a user. By calculating cosine/Pearson similarity, the most similar users are found. Then items liked by similar users are recommended.

2. Item-based Collaborative Filtering
On the contrary, item-based Collaborative Filtering use user ratings as the attributes of an item. By calculating cosine/Pearson similarity, the most similar items are found and recommended.


### 2.5 Recommendation for user
**Recommendation with Item-based Collaborative Filtering**
Take game “Left 4 Dead 2” for example, if a user likes the game (meaning spending a lot of time on it), then based on item-based CF method, below games are recommended because user ratings behave very alike on these games:

![imge1](/images/Picture1.png)

**Recommendation with User-based Collaborative Filtering**
Take userID 151603712 for example, if we want to recommend new games to the user, we will first find the most similar users and recommend their top-rated games to the user. With a step further, user 151603712’s rating for new games are forecasted with user-based CF and the top rated games are recommended as below:

![imge1](/images/Picture2.png)
