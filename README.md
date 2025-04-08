# AI-Powered Suicide Prevention from Reddit

## GSoC 2025 Submission

This project demonstrates an end-to-end pipeline for identifying, analyzing, and visualizing crisis-related content from Reddit, with a focus on mental health and suicide prevention.

## Project Structure

The project consists of three main components:

1. **Data Extraction & Preprocessing** - Extracts and cleans Reddit posts related to mental health crises
2. **Sentiment Analysis & Risk Classification** - Analyzes post sentiment and categorizes risk levels
3. **Geolocation Analysis & Visualization** - Maps crisis discussions by location to identify regional patterns

## Installation & Setup

### Prerequisites
- Python 3.8+
- Google Colab (recommended for easy execution)
- Reddit API credentials

### Required Libraries
```
pip install vaderSentiment gensim pandas matplotlib folium nltk spacy praw geopy plotly
python -m spacy download en_core_web_sm
python -m nltk.downloader punkt stopwords wordnet
```

### Configuration
To use the Reddit API, you need to:
1. Create a Reddit developer account at https://www.reddit.com/prefs/apps
2. Generate API credentials (client ID and client secret)
3. Replace the placeholders in the code with your credentials:
   ```python
   CLIENT_ID = "your_client_id"
   CLIENT_SECRET = "your_client_secret"
   USER_AGENT = "your_app_name"
   ```

## Usage

### 1. Data Extraction (Task 1)
The first script connects to the Reddit API, searches for mental health related keywords in targeted subreddits, and saves both raw and cleaned data to CSV files.

Key features:
- Multi-subreddit search across 5 mental health communities
- Keyword-based filtering with 16 crisis-related terms
- Text preprocessing (URL removal, lemmatization, stopword removal)

### 2. Sentiment Analysis & Risk Classification (Task 2)
The second script analyzes the collected data using NLP techniques:

Key features:
- VADER sentiment analysis for positive/negative/neutral classification
- Word2Vec model for semantic similarity detection
- Risk level classification based on crisis language

### 3. Geolocation Analysis (Task 3)
The third script extracts location information and generates visualizations:

Key features:
- Named Entity Recognition for location extraction
- Geocoding of locations to coordinates
- Interactive heatmap of crisis discussions
- Regional distribution analysis

## Results

The pipeline produces several outputs:
- Cleaned and processed CSV files with sentiment and risk assessments
- Interactive heatmap showing crisis hotspots
- Top 5 locations with highest crisis discussions
- Regional distribution chart

## Future Improvements
- Implement real-time monitoring capabilities
- Develop intervention recommendation system
- Add multi-language support
- Integrate with crisis response systems

## License
This project is submitted as part of the Google Summer of Code 2025 application.

## Acknowledgments
- Reddit API for data access
- NLTK, SpaCy and other open-source NLP libraries
- Folium and Plotly for visualization
