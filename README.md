# Capstone Project: Netflix Recommendation System

This project builds a movie recommendation engine using collaborative filtering and content-based filtering. It utilizes **user rating behavior** and **Netflix title metadata** to provide intelligent movie suggestions tailored to individual users.

---

## 🗂️ Datasets Used

### 1. User Ratings Dataset
📥 [Download here](https://www.kaggle.com/datasets/rishitjavia/netflix-movie-rating-dataset)

- `Cust_Id`: Unique identifier for users.
- `Movie_Id`: Unique identifier for movies.
- `Rating`: User's rating on a scale of 1–5.

### 2. Titles Metadata Dataset
📥 [Download here](https://www.kaggle.com/datasets/shivamb/netflix-shows)

- `title`: Name of the movie or show.
- `type`: Movie or TV Show.
- `release_year`: Year the title was released.
- `listed_in`: Genre(s).
- `description`: Short summary of the content.

These datasets are **manually mapped** using `Movie_Id` and `title` to enrich user preferences with meaningful genre and content information.

---

## 🧠 Project Objectives

1. **Build a recommendation engine** based on user ratings.
2. **Integrate genre and type info** from metadata.
3. **Find most popular and liked titles** across users.
4. **Recommend personalized movies** for specific users.
5. **Analyze content trends** like top-rated genres, release years, etc.

---

## 🧪 Workflow Overview

### 1. Data Preprocessing
- Remove `NaN` ratings.
- Create movie-user matrix.
- Normalize user ratings using MinMaxScaler.
- Merge datasets to enrich `Movie_Id` with `title`, `genre`, etc.

### 2. Recommendation Engine
- Build a **user-item matrix** for collaborative filtering.
- Use **cosine similarity** to compute similar user profiles.
- Predict top movies a user would enjoy based on peer preferences.

### 3. Popularity & Trend Analysis
- Find movies with the **highest number of ratings**.
- Find movies with the **highest average rating**.
- Identify the **most liked genres** and **best performing content types**.

### 4. Personalized Recommendations
- For a given user (e.g. `user_id = 6`), recommend:
  - New movies they haven't rated yet.
  - Their most liked genres or types.
  - Suggestions within favorite genres (using metadata).

---

## 📦 Requirements

Install dependencies using:

```bash
pip install pandas numpy matplotlib scikit-learn scikit-surprise
