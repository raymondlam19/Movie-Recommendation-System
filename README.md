# Movie-Recommendation-System
 Kaggle

---
Recommendation Systems are a type of information filtering systems as they improve the quality of search results and provides items that are more relevant to the search item or are realted to the search history of the user.

They are used to predict the rating or preference that a user would give to an item.

**Simple Recommender:**
* give generalized recommnendations based on movie *genre* and *popularity* only (use *vote_average* & *vote_count* to give a *score*)
* The idea is that movies that are more popular and critically acclaimed will have a higher probability of being liked by the average audience.

**Content Based Recommender:**
* use item metadata, such as genre, director, description, actors, etc., to make these recommendations
* The idea behind is that if a person liked a particular item, he will also like an item that is similar to it.
* compute similarity of movies' text features and suggests movies that are most similar to a particular movie that a user liked
* content features:
    * *Overviews* and *Taglines*
    * *Cast*, *Crew*, *Keywords* and *Genre*
    * Finally, text similarity with *score* prioritising (output: content-similar movies sorted by *score*)
* not really personal as it doesn't capture the personal tastes of a user. Anyone querying our engine with a movie name will receive the same recommendations for that movie.

**Collaborative Filtering:**
* predict what the user like (estimated rating of the unseen movie by the user)
    * training: need a table of users giving ratings on different items(movieid) for training
    * prediction: work purely on user id, movie ID to predict estimated rating of the unseen movie by the user (based on how the other users have predicted the movie)
* use surprise library which is a Python scikit building recommender system
    * similar to sklearn (fit, predict, cv, gridsearchcv)
    * different: sklearn (np.array), surprise (has its own object, load from csv with col must = ['userid', 'itemid', 'rating'])
* [Here more about CF theory](https://blog.xuite.net/metafun/life/131996342-Recommendation+Systems%E5%92%8C%E5%8D%94%E5%90%8C%E9%81%8E%E6%BF%BE%28CF%29%E7%B0%A1%E4%BB%8B)

**Hybrid Recommender**
* more personalized, can return different movie recommendations for different users although the searched movie is the same.
* Content-based + collaborative-filter-based engine
* Input: User ID, movie title
* Output: Content-similar movies sorted by estimated ratings by the particular user
