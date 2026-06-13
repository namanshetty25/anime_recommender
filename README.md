# Anime Recommendation System

A machine learning-powered web application that recommends anime titles based on user preferences using collaborative filtering and content-based filtering techniques.

## 🎯 Overview

This project implements two distinct recommendation algorithms to help anime enthusiasts discover new titles similar to their favorites:

- **Collaborative Filtering**: Recommends anime based on viewing patterns and ratings from similar users
- **Content-Based Filtering**: Recommends anime based on genre similarity and other content attributes

## ✨ Features

- 🎬 Dual recommendation algorithms for diverse suggestions
- 🔍 Search functionality for any anime title in the database
- ⭐ Average rating display for recommended anime
- 🎯 Interactive web interface using Streamlit
- 📊 Support for large-scale anime dataset with user ratings

## 🛠️ Technology Stack

- **Python 3.x**: Core programming language
- **Streamlit**: Interactive web framework
- **Scikit-learn**: Machine learning algorithms
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **SciPy**: Scientific computing (sparse matrices)

## 📦 Installation

### Prerequisites
- Python 3.7 or higher
- pip package manager

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/namanshetty25/Anime_recommender_app.git
   cd Anime_recommender_app
   ```

2. **Install required dependencies**
   ```bash
   pip install streamlit pandas numpy scikit-learn scipy
   ```

3. **Run the application**
   ```bash
   streamlit run app.py
   ```

The application will open in your default web browser at `http://localhost:8501`

## 📊 Data

The application uses two main datasets:

- **anime.csv**: Contains anime metadata including titles, genres, and average ratings
- **rating.csv**: Contains user ratings for different anime titles

### Data Preprocessing

The application performs the following preprocessing steps:

- Removes missing values
- Eliminates duplicate ratings (keeps first occurrence)
- Merges anime metadata with user ratings
- Filters users with at least 50 ratings for collaborative filtering robustness
- Cleans anime names by removing special characters and HTML entities

## 🔧 How It Works

### Collaborative Filtering

1. Creates a user-anime rating matrix
2. Uses K-Nearest Neighbors (KNN) with cosine similarity metric
3. Finds anime rated similarly by other users who rated your anime
4. Recommends the top 5 closest matches

**When to use**: Best when you want recommendations similar to what users with your taste watched

### Content-Based Filtering

1. Extracts genre information from anime metadata
2. Applies TF-IDF vectorization to create genre profiles
3. Computes similarity scores using sigmoid kernel
4. Ranks and recommends the top 10 most similar anime

**When to use**: Best when you want anime with similar genres and themes

## 🚀 Usage

1. **Launch the application** using the command above
2. **Select a recommendation type** from the sidebar:
   - Collaborative Filtering
   - Content-Based
3. **Enter an anime title** (e.g., "Naruto", "Death Note", "One Piece")
4. **Click "Get Recommendations"** to see results
5. **View recommendations** with their average ratings

## 📋 Example

```
Input: "Attack on Titan"
Recommendation Type: Content-Based

Output:
1. Demon Slayer (Average Rating: 8.5)
2. My Hero Academia (Average Rating: 8.3)
3. Jujutsu Kaisen (Average Rating: 8.7)
...
```

## ⚙️ Model Parameters

### Collaborative Filtering
- **Metric**: Cosine Similarity
- **Algorithm**: Brute Force KNN
- **Neighbors**: 6 (returns top 5 recommendations)
- **Minimum User Ratings**: 50

### Content-Based Filtering
- **Vectorizer**: TF-IDF
- **Min Document Frequency**: 3
- **N-gram Range**: (1, 3)
- **Kernel**: Sigmoid
- **Top Recommendations**: 10

## 🎨 Interface

The application features:
- Clean, intuitive Streamlit interface
- Sidebar controls for selecting recommendation type
- Real-time search functionality
- Loading indicators during data processing
- Clear error messages for invalid anime titles
- Formatted output with anime titles and ratings

## 🔍 Helper Functions

- `text_cleaning()`: Removes HTML entities and special characters from anime names
- `load_data()`: Loads and merges anime and rating datasets
- `preprocess_for_collaborative()`: Prepares data for collaborative filtering
- `build_knn_model()`: Trains the KNN model on collaborative filtering data
- `get_collaborative_recommendations()`: Generates recommendations using collaborative filtering
- `preprocess_for_content()`: Prepares data for content-based filtering
- `build_content_model()`: Builds TF-IDF and similarity matrices for content-based filtering
- `get_content_recommendations()`: Generates recommendations using content-based filtering

## 📈 Performance Considerations

- Initial data loading and model building takes a moment on first run
- Collaborative filtering works best with anime that have multiple user ratings
- Content-based filtering provides recommendations for any anime with genre data
- Large dataset handling is optimized using sparse matrices

## 🐛 Troubleshooting

### Anime Not Found Error
- Ensure the anime title exactly matches the database
- Try searching with different capitalization or shorter titles

### Slow Loading Time
- This is normal on first run as models are being built
- Subsequent searches will be faster as models are cached in session memory

### Missing Recommendations
- Some anime may not have enough similar titles in the collaborative dataset
- Try switching to the other recommendation type for better results

## 📝 License

This project is open source and available under the MIT License.

## 👤 Author

**Naman Shetty**
- GitHub: [@namanshetty25](https://github.com/namanshetty25)

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs and issues
- Suggest new features
- Submit pull requests
- Improve documentation

## 🔗 Related Resources

- [Streamlit Documentation](https://docs.streamlit.io/)
- [Scikit-learn KNN](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.NearestNeighbors.html)
- [TF-IDF Vectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html)

## 📞 Support

For issues, questions, or suggestions, please open an issue on the GitHub repository.

---

**Enjoy discovering your next favorite anime! 🍿**
