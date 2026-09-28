# 🎬 Movie Recommendation System

A content-based movie recommender built with **Natural Language Processing (NLP)** and deployed as an interactive **Streamlit** web app. Pick a movie you like, and the app suggests similar titles with posters and details.

---

## 📌 Overview

This project analyzes movie metadata (overview, genres, keywords, cast, and crew) and converts it into numerical vectors using NLP techniques. It then measures how similar movies are to each other using **cosine similarity** and recommends the closest matches.

## ✨ Features

- 🔍 Search or select any movie from the dataset
- 🤖 Get top similar movie recommendations based on content
- 🖼️ Movie posters and backdrops displayed in a clean grid layout
- 🏠 Home feed with browsable movie cards
- ⚡ Fast, lightweight, and easy to run locally

## 🧠 How It Works

1. **Data collection:** Movie data (title, overview, genres, keywords, cast, crew) is loaded from the dataset.
2. **Preprocessing:** Text is cleaned by lowercasing, removing spaces in names, removing stop words and punctuation, and applying stemming.
3. **Tag creation:** Overview, genres, keywords, cast, and crew are merged into a single `tags` column for each movie.
4. **Vectorization:** Tags are converted into numerical vectors using **Bag of Words / TF-IDF**.
5. **Similarity:** **Cosine similarity** is computed between all movie vectors.
6. **Recommendation:** For a selected movie, the most similar movies are returned by highest similarity score.
7. **Posters:** Poster and backdrop images are fetched from the TMDB API and shown in the app.

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3 |
| Data handling | Pandas, NumPy |
| NLP | NLTK, Scikit-learn (CountVectorizer / TfidfVectorizer) |
| Similarity | Cosine similarity (Scikit-learn) |
| Web app | Streamlit |
| Poster data | TMDB API, Requests |

## 📁 Project Structure

```
movie_recommendation_system/
│
├── app.py                 # Streamlit web app
├── requirements.txt       # Python dependencies
├── data/                  # Dataset files
├── notebooks/             # Model building / EDA notebook
├── movies.pkl             # Processed movie data
├── similarity.pkl         # Similarity matrix
├── .gitignore
└── README.md
```

> Adjust the file names above to match your actual project.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/pooja0055/movie_recommendation_system.git
cd movie_recommendation_system
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# Mac / Linux
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add your TMDB API key

Get a free API key from [The Movie Database (TMDB)](https://www.themoviedb.org/settings/api), then create a `.env` file in the project root:

```
TMDB_API_KEY=your_api_key_here
```

> Never commit your API key to GitHub. Make sure `.env` is listed in `.gitignore`.

### 5. Run the app

```bash
streamlit run app.py
```

The app opens at `http://localhost:8501`.

## 📊 Dataset

This project uses the **TMDB 5000 Movies and Credits** dataset (or replace with the dataset you used), containing details such as title, overview, genres, keywords, cast, and crew.

## 🔮 Future Improvements

- Hybrid recommendations combining content-based and collaborative filtering
- Use of transformer embeddings (e.g., Sentence-BERT) for better semantic similarity
- Filters by genre, year, and rating
- User accounts and watchlists
- Deployment on Streamlit Community Cloud

## 🤝 Contributing

Contributions are welcome. Fork the repo, create a feature branch, and open a pull request.

## 👩‍💻 Author

**Pooja Dewangan**
GitHub: [@pooja0055](https://github.com/pooja0055)

## Acknowledgements

- [TMDB](https://www.themoviedb.org/) for the movie data and images
- [Streamlit](https://streamlit.io/) for the web framework
- [Scikit-learn](https://scikit-learn.org/) and [NLTK](https://www.nltk.org/) for NLP tools

> This product uses the TMDB API but is not endorsed or certified by TMDB.
