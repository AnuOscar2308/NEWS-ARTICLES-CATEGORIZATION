## Title:

Multi-Source News Scraping + NLP + Multi-Class Text Classification (ML Modeling)

## Executive Summary:

This project builds an end-to-end pipeline that scrapes news text from multiple online sources across domains (Technology, Sports, Business/Economy, and Medical/Health), cleans and processes the raw text using NLP techniques, and then trains machine learning models to automatically classify new text into the correct category.

After generating domain-wise text files (file1.csv–file4.csv), the outputs were manually appended into a single labelled dataset (Dataset.csv), which served as the modeling source for training and evaluating multiple ML classifiers.

##Business Problem:

Organizations that rely on news and information monitoring (healthcare, finance, tech, media intelligence, consulting) need scalable ways to:

- Organise large volumes of unstructured text

- Identify domain-specific content quickly

- Route articles to the right teams (e.g., health vs business)

- Reduce manual review time.

Manual tagging and categorisation do not scale. The business need is an automated classifier that can label incoming text into the correct domain with reasonable accuracy and consistency.
