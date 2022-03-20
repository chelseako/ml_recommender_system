# Movie Lens Recommender System Application
* Created a collaborative filtering item-based recommender system application that prompts a new user to provide 20 ratings for movies they have seen, predicts the new user's ratings on unrated movies, and outputs the top N number of recommended unrated movies with the highest predicted ratings.
* System aids users in identifying content they are more likely to enjoy, providing a better user experience, and helps movie/tv/entertainment streaming companies attract and maintain customers, increasing revenue.
* Performed exploratory data analysis and data cleaning and preparation on the movies, ratings, users data.
* Compared the use of a standard estimator function and singular value decomposition (SVD) function. Using a truncated matrix with the top 100 movies with the highest number of ratings, the standard estimator function produced a mean absolute error (MAE) of 0.769, while the SVD estimator produces an MAE of 0.787.
* I provided 20 real ratings using the standard and SVD estimator functions and found that the standard estimator produced 5 out of 10 recommended movies I previously watched and enjoyed, while the SVD estimator produced 3 out of 10 movies I previously watched and enjoyed. Thus, the standard estimator appears to be the better estimator.

## Code and Resources Used
**Packages:** numpy, pandas, seaborn, matplotlib, seaborn, collections, sklearn

## Data Cleaning
Data included 100,000 movie ratings on 1,682 unique movies from 943 unique users.
* Examined missing values; excluded one movie with title "unknown"
* Reshaped ratings data into a users by movies data matrix
* Engineered features, including number of ratings per movie, average rating for each movie, and number of ratings per user.

## Data Exploration
Examined the frequencies of cateogorical variables and the distributions and relationships between numeric variables.

![Histograms of Movies Variables](https://github.com/chelseako/ml_recommender_system/blob/main/movie.png)

![Histograms of Users Variables](https://github.com/chelseako/ml_recommender_system/blob/main/user.png)

## Model Building  
* Standard estimator  
* Singular value decomposition (SVD) estimator  

The movies database was truncated to include the top 100 movies with the highest number of ratings. Sorting the movies by number of recommendations increases the likelihood new users will be able to rate movies they have seen. Using this truncated dat matrix, 40 components were identified as capturing 85% of the variance.  
![Percent of variance explained by SVD components](https://github.com/chelseako/ml_recommender_system/blob/main/svd_components.png)

## Model Performance
The mean absolute errors for each estimator function are as follows:

**standard estimator:** 0.769

**SVD estimator:** 0.787

## Recommender system
* Created a function that prompts a new user to input 20 ratings for movies they have seen. Users are asked to rate unseen movies as 0 and the function checks for valid input.
* The ratings are transformed into an input vector the same size as the data matrix and appended to the data matrix.
* The recommend function iterates through the unrated items and gets a predicted score using the standard or SVD estimator and a given similarity function.
* The function then outputs the top N number of movies with the highest predicted ratings, along with the average rating given by other users and the total number of ratings for that movie.

The following top 10 movies were recommended when provided with the same input ratings vector:

**Using the standard estimator**

1. Dante's Peak  
2. The Saint  
3. The Devil's Own  
4. Murder at 1600  
5. Twister  
6. Top Gun  
7. Conspiracy Theory  
8. Mr. Holland's Opus  
9. Phenomenon  
10. Jurassic Park  

**Using the SVD estimator**

1. Aladdin  
2. Phenomenon  
3. Courage Under Fire  
4. Indiana Jones and the Last Crusade  
5. Dances with Wolves  
6. The Devil's Own  
7. The Lion King  
8. The Birdcage  
9. The Saint  
10. Dead Poets Society  

The standard and SVD estimator functions produced somewhat similar results. There were a total of three overlapping movie titles in the top 10 (The Saint, The Devil's Own, and Phenomenon), although all three were in different orders. There are five movies recommended using the standard estimator function that I previously watched and enjoyed, where as there were only three movies recommended by the SVD estimator function that I previously watched and enjoyed. Overall, it appears the standard estimator function is the better estimator function to use for this recommender system.
