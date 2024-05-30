# NLP-Based-Amazon-Product-Recommendation-System
This project aims to create a unique recommendation system that enhances traditional collaborative filtering by filling empty values in the user-item matrix using product descriptions, user details, and product details. By combining deep learning and natural language processing (NLP), this project seeks to achieve more accurate recommendations.

# Problem Statement
The objective of this project is to develop an intelligent recommendation system for Amazon products. The system should leverage product descriptions, user details, and product details to fill gaps in the user-item matrix, enhancing the accuracy of collaborative filtering. The effectiveness of this approach will be evaluated based on the precision and accuracy of the recommendations.

# Methodology
## Dataset
The Amazon User Reviews dataset includes millions of reviews from 1995 to 2015, providing insights into user opinions on a variety of items. The data selected for this project includes reviews from categories such as Beauty, Electronics, Grocery, and Health & Personal Care.

## Data Preprocessing
* Combining Datasets: The individual category datasets are combined into a single dataset.
* Text Standardization: All characters are transformed to lowercase to ensure consistency.
* Stop Word Removal: Common stop words are removed to focus on significant words and phrases.
* Part-of-Speech (POS) Tagging: Grammatical tags are assigned to each word for better lemmatization.
* Lemmatization: Words are reduced to their root forms to improve analysis and interpretation.
* Removing Single Letter and Meaningless Words: Terms with less than three characters and words with characters repeated more than three times are eliminated to improve data quality.
* Exploratory Data Analysis (EDA)
* Distribution of Product Categories: Visual representation of review distribution across product categories.
* Distribution of Star Ratings: Histogram showing the distribution of different star ratings.
* Vocabulary Size: Analysis of the total number of words and unique words in the dataset.
* Most Repeated Words: Identification of the top 10 most repeated words after preprocessing.

## Feature Selection
Features for the Recurrent Neural Network (RNN) model include:
* TF-IDF Vectors: Transforming reviews into TF-IDF vectors using a vocabulary size of 64,648.
* Label Encoding: Numerical encoding of customer IDs and product IDs.
* One-Hot Encoding: Converting ratings into a suitable format for model training.

## Model Architecture
LSTM (Long Short-Term Memory) is utilized in the recommendation system due to its effectiveness in processing textual data and capturing specific features. This approach is specifically chosen for recommending product categories based on its ability to handle text sequences and extract relevant information. LSTMs excel in sequential data processing, understanding the order of user actions or item sequences to make accurate recommendations. They also model long-term dependencies, remembering past interactions over extended sequences, allowing for predictions of future preferences. By analyzing past interactions, LSTMs provide personalized recommendations tailored to each user's unique interests. The model includes input layers for item data and category labels. Item data is reshaped to fit an LSTM layer, which predicts sequence patterns. Following the LSTM layer, some information is discarded to prevent overfitting, while labels are flattened. These sets are combined and reshaped for category prediction. Training optimizes internal settings using RMSprop, with batches of size 64 and validation data for performance evaluation. Post-training, the model achieved 59% accuracy in categorization for both seen and unseen data.

# How Users Provide Recommendations?
To provide recommendations, a sample of 50 users and 50 items is selected, constructing a user-item matrix by populating cells with ratings given by these users for the products. Since not every user rates all products, a model predicts ratings for all items, thereby filling in empty values (NaN) in the matrix for improved accuracy. The recommendation process involves two key approaches: calculating the average ratings of all products using the matrix and recommending products with the highest average ratings, and utilizing collaborative filtering by applying cosine similarity to the matrix to identify users with similar preferences to the selected user. Products favored by these similar users are then recommended, leveraging shared interests to enhance the recommendation process.

# Performance and Results
The LSTM classification model achieved an overall accuracy of 59.2%. Detailed performance metrics, including precision, recall, and F1-score, were calculated across different rating classes, highlighting areas for improvement.

# Discussion
The recommendation system successfully integrates deep learning and NLP to enhance traditional collaborative filtering. By analyzing product descriptions and user details, the system provides more accurate recommendations, improving customer satisfaction and business value.

# Conclusion
The project demonstrates the potential of combining deep learning and NLP for developing robust recommendation systems. The model's accuracy and precision indicate its capability to provide valuable insights for e-commerce platforms, enhancing user experience and boosting sales. Further refinement and optimization can improve the model's predictive prowess, making it a valuable tool for personalized recommendations.

# Tools and Technologies
* Python
* Natural Language Processing (NLP)
* Recurrent Neural Networks (RNN)
* Long Short-Term Memory (LSTM) networks
* TF-IDF
* Cosine Similarity
