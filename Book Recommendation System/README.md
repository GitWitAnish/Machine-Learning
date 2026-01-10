# Book Recommendation System

A practical notebook-based project for building and evaluating book recommendations using user ratings. The workflow focuses on data preparation, exploratory analysis, baseline popularity models, and collaborative filtering approaches, with clear guidance to run and extend the experiments.

## Project Structure

- [notebook/main.ipynb](notebook/main.ipynb): Primary experimentation notebook.
- [dataset/](dataset/): Input CSV files used by the notebook.
  - [Books.csv](dataset/Books.csv)
  - [Ratings.csv](dataset/Ratings.csv)
  - [Users.csv](dataset/Users.csv)
- [models/](models/): folder for saving trained artifacts.

## Dataset

The project expects three CSVs:

- Books: Book identifiers and metadata (e.g., title, author, year, publisher).
- Ratings: User–book explicit ratings (e.g., `user_id`, `book_id`, `rating`).
- Users: User identifiers and optional demographics (e.g., age, location).

Note: Column names may vary. Adjust the notebook's loading and column references accordingly in its first data preparation cells.

## Approaches Covered

- Popularity baseline: Recommend most-rated or highest-average-rated books.
- User–Item collaborative filtering: Neighborhood (k-NN) style or matrix-factorization style.
- Top-N recommendation and/or rating prediction depending on the path chosen in the notebook.

## Running the Notebook

- Open [notebook/main.ipynb](notebook/main.ipynb) in VS Code or Jupyter.
- Ensure CSV paths in the first cells point to [dataset/](dataset/).
- Run cells sequentially; inspect outputs, metrics, and sample recommendations.
