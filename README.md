# Enhancing-AI-Generated-Text-Undetectability

This project aims to classify text data based on its origin (human or generated) and improve generated text to appear more human-like using multiple token replacement strategies. The process includes loading and preprocessing data, training a classification model, evaluating its performance, and applying various strategies to enhance generated text's readability and human-likeness.

Table of Contents
Requirements
Data
Pipeline Overview
Data Preprocessing
Model Training and Evaluation
Human-like Text Replacement Strategies
Explainability Using SHAP
Results
Usage
License
Requirements
Python 3.x
Required Libraries: pandas, numpy, nltk, sklearn, xgboost, gensim, openai, matplotlib, seaborn, shap
Install the libraries using:

bash
Copy code
pip install pandas numpy nltk scikit-learn xgboost gensim openai matplotlib seaborn shap
Ensure nltk has the required datasets by running:

python
Copy code
nltk.download('stopwords')
nltk.download('punkt')
Data
Place the CSV files in the Data/ directory with names such as dev_en_news.csv, dev_en_reviews.csv, etc. Each file should contain columns label (1 for generated, 0 for human) and text.

Pipeline Overview
Data Preprocessing
Load CSV files containing text data in English and Dutch across various domains (news, reviews, Twitter).
Clean and tokenize text, removing stop words and converting to lowercase.
Split data into training and testing sets.
Vectorize text using TF-IDF.
Model Training and Evaluation
Training: Trains an XGBoost classifier on the processed text data.
Evaluation: Computes precision, recall, F1-score, and accuracy, reporting overall performance and language/domain-specific metrics.
Human-like Text Replacement Strategies
To make generated text more human-like, we apply the following strategies:

Similar Human Word Replacement: Use a Word2Vec model trained on human text to replace tokens with similar words used by humans.
POS-Based Replacement: Matches similar words based on Part of Speech (POS) tags.
GPT-4 Replacement: Uses GPT-4 to suggest replacements for tokens in the text.
Genre-Specific GPT-4 Replacement: Customizes replacements for each genre (e.g., news, reviews) using GPT-4.
Explainability Using SHAP
The SHAP (SHapley Additive exPlanations) library identifies influential tokens for the classification model.
Outputs top tokens impacting classification results and a summary plot for interpretability.
Results
The results of each strategy are saved in CSV files (e.g., strategy1_results.csv, strategy2_results.csv). Visualizations include:

Metrics per language and genre
Token importance (SHAP values) for the top influential tokens
Comparison of classification metrics across replacement strategies
Usage
To run the code, ensure all dependencies are installed, place data in the Data/ directory, and set up your OpenAI API key for GPT-4 functionality. Execute the script and view the console for metrics reports and generated visualizations.

License
This project is licensed under the MIT License. See LICENSE for details.

