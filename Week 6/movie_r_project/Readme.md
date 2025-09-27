# movie-recommender-system-tmdb-dataset

A content-based movie recommender system using cosine similarity. The dataset used is taken from [Here](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata?select=tmdb_5000_movies.csv).

## 🎬 Overview

This project implements a movie recommendation system that suggests similar movies based on content features like genres, keywords, cast, crew, and plot overview. The system uses **cosine similarity** to find movies with similar characteristics and provides personalized recommendations.

## 🚀 Features

- **Content-Based Filtering**: Recommends movies based on movie features rather than user ratings
- **Text Processing**: Combines multiple movie features (genres, keywords, cast, crew, overview) into a single feature vector
- **Cosine Similarity**: Uses mathematical similarity to find related movies
- **Interactive CLI**: Simple command-line interface for getting recommendations
- **Pickle Storage**: Save and load the trained model for quick access

## 📊 Dataset

The system uses the **TMDB 5000 Movie Dataset** which contains:
- **tmdb_5000_movies.csv**: Movie metadata including budget, genres, overview, popularity, etc.
- **tmdb_5000_credits.csv**: Cast and crew information for each movie

**Key Features Used:**
- Movie Title
- Overview (Plot summary)
- Genres
- Keywords
- Cast (Top actors)
- Crew (Director, etc.)

## 🛠️ Installation

### Prerequisites
```bash
pip install pandas numpy sklearn pickle
```

### Setup
1. Clone the repository:
```bash
git clone https://github.com/Abdullah-056/90-days-with-Buildables.git
cd Week 6/movie_r/
```

2. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata) and place the CSV files in the project directory.

3. Run the preprocessing script to generate the model:
```bash
python movie_pred.ipync
```

4. Or you can directly use `movie_list.pkl` file and `similarity.pkl`.


## 🔧 How It Works

### 1. **Data Preprocessing**
- Combines movie features (overview, genres, keywords, cast, crew) into a single text string
- Removes unnecessary columns and cleans the data

### 2. **Feature Extraction**
- Uses `CountVectorizer` to convert text data into numerical vectors
- Limits to top 5000 features and removes English stop words
- Creates a matrix where each row represents a movie and columns represent word frequencies

### 3. **Similarity Calculation**
- Applies **Cosine Similarity** to measure similarity between movie vectors
- Creates a similarity matrix where each cell represents how similar two movies are (0-1 scale)

### 4. **Recommendation Generation**
- For a given movie, finds the most similar movies based on cosine similarity scores
- Returns the top N most similar movies as recommendations


## 🎯 Example Recommendations

**Input:** "The Avengers"
**Output:**
1. Iron Man
2. Captain America: The First Avenger
3. Iron Man 2
4. Thor
5. Guardians of the Galaxy

**Input:** "Titanic"
**Output:**
1. The Notebook
2. A Walk to Remember
3. Dear John
4. The Vow
5. Safe Haven

## 🔍 Technical Details

- **Algorithm**: Content-Based Filtering with Cosine Similarity
- **Vector Space**: 5000-dimensional feature space
- **Similarity Metric**: Cosine Similarity (range: 0-1)
- **Text Processing**: CountVectorizer with English stop words removal
- **Storage**: Pickle files for model persistence

## 🚧 Future Enhancements

- [ ] Add collaborative filtering for hybrid recommendations
- [ ] Implement web interface using Flask/Streamlit
- [ ] Add movie posters and additional metadata
- [ ] Include user ratings and reviews
- [ ] Implement advanced NLP techniques (TF-IDF, Word2Vec)
- [ ] Add recommendation explanations
- [ ] Support for multiple languages
