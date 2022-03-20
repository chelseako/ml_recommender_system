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
Examined the distributions and relationships between numeric variables.

## Model Building
* Standard estimator
* Singular value decomposition (SVD) estimator

## Model Performance
* **MAE for standard estimator:** 0.769
* **MAE for SVD estimator:** 0.787
