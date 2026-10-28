# Book and Movie Recommender

## 1. Project Overview

This project develops a simple academic recommendation system for books and movies. It aims to help users discover relevant items based on their interests and the content features of books and movies.

## 2. Problem Statement

Users often face a large number of books and movies and may find it difficult to identify items that match their interests. The goal of this project is to build a system that ranks and recommends relevant books and movies using their available metadata and content features.

## 3. Initial Approach

The initial baseline will use content-based filtering:

- Represent items using text features such as genres, titles, and descriptions when available.
- Convert text into numerical feature vectors using TF-IDF.
- Calculate cosine similarity between items.
- Rank candidate items by similarity to a user's selected or preferred items.

The initial implementation is an academic prototype, not a production recommendation service.

## 4. PEAS Description

| Component | Description |
|---|---|
| Performance measure | Relevance of recommendations, Precision@K on an appropriate labeled test set when available, and successful execution of the recommendation pipeline |
| Environment | A catalog containing books and movies, their metadata, and user-selected preferences |
| Actuators | Displaying and ranking recommended books and movies |
| Sensors | User-selected items or preferences and available item metadata |

## 5. Environment Properties

The recommendation environment is initially described as follows:

1. **Partially observable:** The system cannot know all of a user's interests from limited preferences.
2. **Single-agent:** The prototype generates recommendations for one user at a time without competing agents.
3. **Deterministic (baseline assumption):** Given the same catalog, preferences, and configuration, the baseline produces the same rankings.
4. **Sequential:** A user's selections can influence later recommendations.
5. **Static (baseline assumption):** The catalog is treated as unchanged during a single recommendation run.
6. **Discrete:** Items, user selections, and recommendation rankings are represented as discrete records.

These are modeling assumptions for the initial prototype and may change if the project scope changes.

## 6. Evaluation

The initial evaluation plan is to verify that the recommendation pipeline runs correctly and returns ranked results. If a suitable labeled test set is available, Precision@K will be used to evaluate the relevance of the top-K recommendations.

Evaluation results will be reported only after the test data and evaluation procedure have been defined.

## 7. Risks and Mitigations

1. **Incomplete or inconsistent metadata:** Some items may lack descriptions or genres. Mitigation: inspect missing values and document the cleaning rules.
2. **Data licensing and source restrictions:** Dataset usage may be limited by its license or terms. Mitigation: document each source and verify its permitted use before including data.
3. **Limited evaluation data:** There may not be enough reliable relevance labels to evaluate recommendations. Mitigation: define a transparent test procedure and clearly distinguish real labels from synthetic examples.

## 8. Project Scope

- A shared catalog for books and movies.
- Python implementation.
- Reproducible data preparation and evaluation.
- A content-based baseline using TF-IDF and cosine similarity.
- An academic prototype rather than a production service.

## 9. Repository Structure

- `data/raw/`: source data, excluded from Git by default.
- `data/processed/`: generated data, excluded from Git by default.
- `notebooks/`: exploratory analysis and environment checks.
- `src/`: reusable project code.
- `tests/`: tests.
- `reports/`: project reports.

## 10. Project Status

Step 1 is in progress. The problem definition, environment model, evaluation plan, and risks must be reviewed alongside the environment-check notebook before Step 1 is considered complete.