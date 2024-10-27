# Project Title: Product Review Analysis on Digikala Using Hazm and ElasticSearch

## Overview
This project focuses on analyzing user reviews for the top-selling product on Digikala. The steps involve web scraping, natural language processing, and sentiment analysis, with data stored and indexed in ElasticSearch. The Hazm library, specialized for Persian language processing, is used to perform various NLP tasks. 

## Steps

1. **Data Collection**:
   - Scrape reviews of the top-selling product on Digikala.
   - Store the reviews in ElasticSearch for easy indexing and retrieval.

2. **Data Processing with Hazm**:
   - **Normalization**: Clean and standardize text.
   - **Segmentation and Tokenization**: Divide reviews into sentences and words.
   - **Stemming and POS Tagging**: Extract the root of each word and tag each with its Part of Speech (POS).
   - **POS Candidate Extraction**: Extract and tag candidates from each word for further processing.
   - **Cosine Similarity**: Calculate similarity scores for each candidate compared to the overall text and other candidates using the Sent2Vec model.
   - **Keyword Extraction**: Identify keywords based on cosine similarity scores.

3. **Sentiment Analysis**:
   - Classify comments into positive and negative categories.
   - Calculate the percentage of positive and negative comments.
   - Implement a KNN model with 80% of the data as the training set and report model performance.

4. **Data Storage**:
   - Store processed data in ElasticSearch with separate indices for each analysis step.
   - Provide reasoning for indexing choices to optimize retrieval and analysis.

## Tools & Libraries
- **Hazm**: Persian text processing.
- **ElasticSearch**: For storing and indexing scraped and processed data.
- **KNN & Sent2Vec**: Machine learning models for sentiment analysis and keyword extraction.

## Notes
Refer to the [Hazm Package](https://github.com/sobhe/hazm) documentation for additional details on Persian NLP capabilities.

