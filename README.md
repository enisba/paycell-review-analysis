# Paycell User Review Analysis: Sentiment Classification and Semantic Clustering

This project presents a complete pipeline for analyzing user feedback of the **Paycell** mobile application. The goal is to extract meaningful insights from app reviews, identify pain points in the user experience, and monitor how user sentiment has evolved over time — especially around version updates.

##  Project Structure

- **01_scraping.ipynb**  
  I scraped ~68,000 user reviews from the Google Play Store using a custom scraper. Metadata like timestamps, ratings, and review text were also collected (`paycell_reviews_play_store.csv`).

- **02_preprocessing.ipynb**  
  Reviews were cleaned and normalized. I removed non-alphabetical characters, converted to lowercase, filtered stopwords, and used **Zemberek NLP** for lemmatization. Outputs are stored in `preprocessed_review.csv` and `cleaned_reviews.csv`.

- **03_modeling.ipynb**  
  I used a pre-trained multilingual transformer model (`nlptown/bert-base-multilingual-uncased-sentiment`) to perform sentiment classification. The output file `sentiment_results.csv` contains the predicted label for each review: **positive**, **neutral**, or **negative**.

- **04_visualization.ipynb**  
  I visualized sentiment trends over time and across app versions. I also performed **semantic clustering** on negative reviews using TF-IDF and KMeans to identify the most recurring themes of dissatisfaction.

##  Datasets Used

| File | Description |
|------|-------------|
| `paycell_reviews_play_store.csv` | Raw scraped reviews from the Google Play Store |
| `cleaned_reviews.csv` | Cleaned text after removing noise and stopwords |
| `preprocessed_review.csv` | Lemmatized and fully processed version of user reviews |
| `sentiment_results.csv` | Final sentiment prediction results |
| `paycell_update_history_app_store_labeled.csv` | Version history of the app with update dates and manually labeled version windows for trend mapping |

##  Methods & Tools

- **Language:** Python (Jupyter Notebooks)
- **Libraries:** pandas, numpy, sklearn, matplotlib, seaborn, transformers
- **NLP Preprocessing:** Zemberek NLP (Java-based library for Turkish lemmatization)
- **Modeling:** Transformer-based sentiment classification
- **Clustering:** TF-IDF + KMeans on negative reviews
- **Visualization:** Trend plots, pie charts, bar plots

##  Goals

- Understand how user sentiment evolves across different app versions.
- Identify clusters of dissatisfaction using semantic grouping.
- Demonstrate how real-world user feedback can be used to guide product development decisions in fintech apps.

## Notes

- Some reviews are sarcastic, short, or ambiguous, this may reduce model accuracy.
- App versions with fewer comments may introduce fluctuations in the time series graphs.
- Sentiment model is not fine-tuned on Turkish, but performs reasonably well with multilingual structure.

---

