# Movie Lens Recommender System Application
* Created a collaborative filtering recommender system application that prompts a new user to provide 20 ratings for movies they have seen, compares the given ratings to ratings given by other users using a similarity function, predicts new users' ratings on unrated movies, and outputs the top N number of recommended unrated movies.
* Users can enter 0 if they have not yet seen the presented movie, and the function checks input to ensure valid ratings.
* System can aid users in identifying content they are more likely to enjoy, providing a better user experience, and can help streaming/movie companies attract and maintain customers, increasing revenue.
* Performed exploratory data analysis and data cleaning and preparation on the movies, ratings, users data.
* Compared the use of a standard estimator function and singular value decomposition (SVD) function. Using a truncated matrix with the top 100 movies with the highest number of ratings, the standard estimator function produced a mean absolute error (MAE) of 0.769, while the SVD estimator produces an MAE of 0.787.
* I provided 20 real ratings using the standard and SVD estimator functions and found that the standard estimator produced 5 out of 10 movies I previously watched and enjoyed, while the SVD estimator produced 3 out of 10 movies I previously watched and enjoyed. Thus, the standard estimator appears to be the better estimator.

## Code and Resources Used
**Packages:** numpy, pandas, seaborn, matplotlib, seaborn, collections, sklearn

## Data Cleaning
Data included 100,000 movie ratings on 1,682 unique movies from 943 unique users.
* 
