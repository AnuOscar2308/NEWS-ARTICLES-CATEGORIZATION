## Title:

Multi-Source News Scraping + NLP + Multi-Class Text Classification (ML Modeling)

## Executive Summary:

This project builds an end-to-end pipeline that scrapes news text from multiple online sources across domains (Technology, Sports, Business/Economy, and Medical/Health), cleans and processes the raw text using NLP techniques, and then trains machine learning models to automatically classify new text into the correct category.

After generating domain-wise text files (file1.csv–file4.csv), the outputs were manually appended into a single labelled dataset (Dataset.csv), which served as the modeling source for training and evaluating multiple ML classifiers.

## Business Problem:

Organizations that rely on news and information monitoring (healthcare, finance, tech, media intelligence, consulting) need scalable ways to:

- Organise large volumes of unstructured text

- Identify domain-specific content quickly

- Route articles to the right teams (e.g., health vs business)

- Reduce manual review time.

Manual tagging and categorisation do not scale. The business need is an automated classifier that can label incoming text into the correct domain with reasonable accuracy and consistency.
## Methodology:

#### 1) Data Collection (Web Scraping)

- Scraped HTML content from multiple news sources using requests

- Parsed and extracted readable text using BeautifulSoup

### 2) Text Cleaning

- Removed scripts/styles and HTML tags

- Extracted clean visible text using a reusable cleaning function (remove_tags())

### 3) NLP Preprocessing (Feature Preparation)

- Tokenized text (regex/NLTK tokenizers)

- Normalized tokens (lowercasing)

- Removed stopwords (NLTK English stopwords)

- Generated exploratory frequency distributions (NLTK FreqDist) to understand dominant terms per category

### 4) Dataset Construction

- Exported tokens/text into CSVs:

  - file1.csv (Technology)

  - file2.csv (Sports)

  - file3.csv (Business/Economy)

  - file4.csv (Medical/Health)

- Manually appended these category files into a single labeled dataset: Dataset.csv

- Columns used in modeling: Text, Category

### 5) ML Data Modeling (Supervised Learning)

- Encoded labels:

  - Created CategoryId using factorize()

- Train/test split:

  - 70/30 split using train_test_split(shuffle=True, random_state=0)

- Vectorization (Feature Engineering):

  - Converted raw text into numeric features using Bag-of-Words

  - CountVectorizer(max_features=5000) → document-term matrix

 ### 6) Model Training & Evaluation

Trained and evaluated multiple baseline classifiers (wrapped in OneVsRestClassifier for multi-class):

- Logistic Regression

- Random Forest

- Multinomial Naive Bayes

- Support Vector Classifier (SVC)

- Decision Tree

- K-Nearest Neighbors

- Gaussian Naive Bayes

Metrics reported:

- Accuracy

- Precision (micro)

- Recall (micro)

- F1-score (micro)

### 7) Prediction Demo

Trained a final Random Forest classifier and predicted the category of sample headlines by transforming text via the trained CountVectorizer.
