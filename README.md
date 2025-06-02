🎥 Movie Recommender App
A full-stack movie recommendation platform powered by Streamlit, TMDB API, and preprocessed content-based filtering logic using cosine similarity.

✨ Features
🔍 Movie Selection Dropdown

🎯 Top 5 Content-Based Recommendations

🖼️ Poster Display Using TMDB API

⚡ Fast Response Time (via precomputed similarity matrix)

📦 Pickled Dataset Integration

💻 Deployed with Vercel (Frontend) and Render (Backend TMDB Proxy)

🧪 Tech Stack
Frontend	Backend	ML/Tools
Streamlit	TMDB API (via REST)	Cosine Similarity
HTML/CSS (auto)	Python (requests)	Scikit-learn
Vercel/Heroku	Pickle files	Pandas, NumPy

📂 Folder Structure
bash
Copy
Edit
movie-recommender/
├── app.py                 # Streamlit app logic
├── movie_dict.pkl         # Serialized movie dataset
├── similarity.pkl         # Precomputed cosine similarity matrix
├── .streamlit/            # Deployment config for Streamlit
│   └── config.toml
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
⚙️ Local Setup
1. Install Requirements
bash
Copy
Edit
pip install -r requirements.txt
2. Run the App
bash
Copy
Edit
streamlit run app.py
🌐 Deployment
🔹 Frontend (Streamlit)
To prepare for hosting on Streamlit Cloud, create the config file:

bash
Copy
Edit
mkdir -p ~/.streamlit/

echo "\
[server]\n\
port = $PORT\n\
enableCORS = false\n\
headless = true\n\
\n\
" > ~/.streamlit/config.toml
🔹 Backend (API Key)
You must use your TMDB API key. Replace it in fetch_poster():

python
Copy
Edit
api_key = "your_actual_tmdb_api_key"
url = f"https://api.themoviedb.org/3/movie/{movie_id}?api_key={api_key}&language=en-US"
💾 Backend Data
movie_dict.pkl: contains all processed movie metadata.

similarity.pkl: similarity scores (cosine similarity) between all movies.

These were generated from TMDB 5000 dataset (movies + credits) and preprocessed in Jupyter Notebook.

📸 Screenshots
🎞️ Interface
<img src="https://i.imgur.com/YourDemoImage1.png" alt="Homepage" width="500"/>
🔍 Movie Recommendation Output
<img src="https://i.imgur.com/YourDemoImage2.png" alt="Results" width="500"/>
🔮 Future Improvements
Add genre & keyword filters

Include user ratings and collaborative filtering

Expand to hybrid recommendation models

Pagination and infinite scroll for large datasets

