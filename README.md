# Movie Recommendation System

## Project Overview

This project implements a movie recommendation system using the MovieLens Latest Small dataset. It explores user rating patterns and uses user-based collaborative filtering to predict ratings and recommend movies.

The collaborative filtering model is compared with a simple baseline that predicts ratings using each movie's average rating in the training dataset.

## Objectives

- Explore and analyze movie rating data.
- Understand user preferences and rating patterns.
- Build a user-based collaborative filtering recommendation model.
- Evaluate recommendation performance using MAE and RMSE.
- Compare collaborative filtering with a baseline model.
- Identify the system's limitations and ethical considerations.

## Dataset

The project uses the **MovieLens Latest Small** dataset.

The main files are:

- `movies.csv`: movie IDs, titles, and genres.
- `ratings.csv`: user IDs, movie IDs, ratings, and timestamps.

The dataset contains approximately 9,700 movies and 100,000 ratings from 610 users.

## Methods

### 1. Data Exploration and Preprocessing

The data is inspected for missing values, duplicate records, rating distributions, and consistency between movie IDs and ratings. The ratings are divided into training and test sets, with an 80/20 split for each user.

### 2. Baseline Model

The baseline predicts a movie's rating using its average rating in the training set.

### 3. User-Based Collaborative Filtering

A user-item rating matrix is created from the training data. Cosine similarity is used to measure similarity between users. Ratings from similar users are then combined to predict a user's rating for a movie.

The current implementation considers the 20 most similar users and requires at least three neighbors who have rated the target movie.

## Evaluation

The models are evaluated using:

- **Mean Absolute Error (MAE):** measures the average absolute difference between predicted and actual ratings.
- **Root Mean Squared Error (RMSE):** measures prediction error while penalizing larger errors more heavily.

Both models were evaluated on the same 13,562 test ratings.

| Metric | Baseline | Collaborative Filtering |
|---|---:|---:|
| MAE | 0.7175 | 0.7276 |
| RMSE | 0.9252 | 0.9420 |

Lower values indicate better rating prediction accuracy. In this experiment, the baseline performed slightly better than the current collaborative filtering model.

## Limitations

- The rating matrix is sparse.
- New users and movies may have insufficient rating history.
- The current collaborative filtering model does not outperform the baseline.
- Predictions require enough similar users who have rated a movie.
- Recommendations may reflect biases in the dataset.

## Ethical Considerations

User rating histories may reveal personal interests and should be handled responsibly. Recommendations are based on patterns in the available data and should be treated as suggestions, not objective assessments of movie quality.

## Project Structure

```text
book-movie-recommender/
├── data/
│   ├── movies.csv
│   └── ratings.csv
├── notebooks/
│   └── inspect_data.ipynb
├── README.md
└── .gitignore
```

## Technologies

- Python
- pandas
- NumPy
- scikit-learn
- Jupyter Notebook
- Matplotlib

## How to Run

1. Clone or download the repository.
2. Install the required Python libraries.
3. Ensure the MovieLens CSV files are in the `data/` directory.
4. Open `notebooks/inspect_data.ipynb` in Jupyter Notebook.
5. Run the notebook cells in order.

## Conclusion

This project demonstrates the development and evaluation of a movie recommendation system. The experiment shows that a simple movie-average baseline can outperform a basic user-based collaborative filtering model. Future improvements could include testing different neighborhood sizes, adjusting for user rating tendencies, and exploring alternative recommendation algorithms.
