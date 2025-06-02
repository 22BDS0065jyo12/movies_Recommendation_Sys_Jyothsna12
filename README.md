
title: "🎥 Movie Recommender App"
output: github_document

# 🎥 Movie Recommender App

A **full-stack movie recommendation platform** powered by `Streamlit`, `TMDB API`, and **content-based filtering** using **cosine similarity**.

## ✨ Features

- 🔍 Movie Selection Dropdown  
- 🎯 Top 5 Content-Based Recommendations  
- 🖼️ Poster Display Using TMDB API  
- ⚡ Fast Response Time (precomputed similarity matrix)  
- 📦 Pickled Dataset Integration  
- 🚀 Deployable via **Vercel** (Frontend) and **Render** (Backend for TMDB Proxy)

## 🧪 Tech Stack

| Frontend        | Backend           | ML/Tools        |
|----------------|-------------------|-----------------|
| Streamlit      | TMDB API (REST)   | Cosine Similarity |
| HTML/CSS (auto)| Python + Requests | Scikit-learn     |
| Vercel         | API Key Injection | Pandas, NumPy    |

## 📂 Folder Structure

movie-recommender/
├── app.py                # Streamlit app logic
├── movie_dict.pkl        # Serialized movie dataset
├── similarity.pkl        # Cosine similarity matrix
├── .streamlit/
│   └── config.toml       # Streamlit deployment config
├── requirements.txt      # Python dependencies
└── README.Rmd            # RMarkdown project documentation

⚙️ Local Setup
1. Install Requirements --> pip install -r requirements.txt
2. Run the App Locally --> streamlit run app.py

## 🌐 Deployment Instructions

### 🔹 Frontend: Streamlit Cloud or Vercel

```bash
mkdir -p ~/.streamlit/

echo "\
[server]\n\
port = \$PORT\n\
enableCORS = false\n\
headless = true\n\
" > ~/.streamlit/config.toml
💾 Backend Data
movie_dict.pkl
Contains a pickled pandas.DataFrame of movie metadata (title, id, etc.).

similarity.pkl
Stores a precomputed cosine similarity matrix (2D array of similarity scores between movies).

These files are derived from the TMDB 5000 Movie Dataset (movies and credits) and processed using a Jupyter Notebook pipeline.
