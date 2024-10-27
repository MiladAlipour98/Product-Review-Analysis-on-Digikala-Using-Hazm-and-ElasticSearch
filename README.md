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

### Results and Conclusion

The following results were achieved for keyword extraction and sentiment classification:

1. **Keyword Extraction and Embedding**:
   - Extracted keywords were saved to `keywords.csv` for analysis and future reference.
   - Using FastText word embeddings (`fasttext_skipgram_300.bin`), each keyword was transformed into a 300-dimensional vector.
   - These vectors were aggregated to form a 1500-dimensional feature vector for each comment.

2. **Data Preparation for Model Training**:
   - The final dataset had 413 samples, with each feature vector reshaped to dimensions `(413, 1500)` for compatibility with machine learning models.
   - Labels were stored as `y`, with shapes `(413,)`, representing the sentiment of each comment.

3. **KNN Model Training and Evaluation**:
   - After splitting the data with an 80-20 train-test ratio, a K-Nearest Neighbors (KNN) model was trained with `n_neighbors=5`.
   - Model performance was evaluated, achieving:
     - **Training Accuracy**: 91.5%
     - **Testing Accuracy**: 91.6%

This high accuracy on both training and testing sets indicates that the model effectively learned the patterns in the comment data, showing strong generalization for sentiment classification.
