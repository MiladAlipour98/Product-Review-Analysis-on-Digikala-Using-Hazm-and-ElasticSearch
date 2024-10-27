Data Collection:

Scrape reviews of the top-selling product on Digikala.
Store the reviews in ElasticSearch for easy indexing and retrieval.
Data Processing with Hazm:

Normalization: Clean and standardize text.
Segmentation and Tokenization: Divide reviews into sentences and words.
Stemming and POS Tagging: Extract the root of each word and tag each with its Part of Speech (POS).
POS Candidate Extraction: Extract and tag candidates from each word for further processing.
Cosine Similarity: Calculate similarity scores for each candidate compared to the overall text and other candidates using the Sent2Vec model.
Keyword Extraction: Identify keywords based on cosine similarity scores.
Sentiment Analysis:

Classify comments into positive and negative categories.
Calculate the percentage of positive and negative comments.
Implement a KNN model with 80% of the data as the training set and report model performance.
Data Storage:

Store processed data in ElasticSearch with separate indices for each analysis step.
Provide reasoning for indexing choices to optimize retrieval and analysis.
Tools & Libraries
Hazm: Persian text processing.
ElasticSearch: For storing and indexing scraped and processed data.
KNN & Sent2Vec: Machine learning models for sentiment analysis and keyword extraction.
Notes
Refer to the Hazm Package documentation for additional details on Persian NLP capabilities.
