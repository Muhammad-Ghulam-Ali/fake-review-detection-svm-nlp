# fake-review-detection-svm-nlp
A machine learning project for detecting fake product reviews using NLP, TF-IDF vectorization, and Support Vector Machines (SVM) on the Amazon Fine Food Reviews dataset.
# Fake Review Detection using NLP and Support Vector Machines (SVM)

This repository contains a complete machine learning pipeline for detecting fake product reviews using natural language processing and Support Vector Machines. The solution is built using the Amazon Fine Food Reviews dataset and simulates real-world review manipulation detection using custom labeling heuristics.

---

## 📌 Project Objective

To identify fake vs genuine reviews in an e-commerce setting using engineered behavioral features and textual patterns. In the absence of labeled data, rule-based heuristics are designed to generate realistic labels.

---

## 📂 Dataset

- **Source**: [Amazon Fine Food Reviews – Kaggle](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)
- **Size**: ~568,000 reviews
- **Fields Used**: `Text`, `UserId`, `HelpfulnessNumerator`, `HelpfulnessDenominator`

---

## 🧠 Labeling Strategy

Since the dataset lacks labels, reviews are marked as *Fake (0)* or *Genuine (1)* using the following logic:

### Marked as **Fake (0)** if:
- User has only one review
- Review length is < 20 words
- HelpfulnessDenominator == 0
- Text is a duplicate

### Marked as **Genuine (1)** if:
- User has multiple reviews
- Review is detailed
- Review received helpfulness votes
- Text is unique

This emulates how real platforms like Amazon may flag suspicious reviews.

---

## 🔧 Preprocessing & Feature Engineering

- Text cleaning: lowercasing, punctuation removal, lemmatization
- Feature construction:
  - `review_word_count`
  - `duplicate_text`
  - `user_review_count`
  - `helpfulness_ratio`

---

## 🗃️ Vectorization

- **TF-IDF** (Term Frequency–Inverse Document Frequency) is used to convert the cleaned reviews into numeric vectors suitable for model training.

---

## ⚖️ Handling Imbalance

- **SMOTE** (Synthetic Minority Oversampling Technique) is applied to address class imbalance by oversampling fake reviews.

---

## 🤖 Model: Support Vector Machine (SVM)

- **Classifier**: `LinearSVC` from scikit-learn
- **Train/Test Split**: 80/20 with stratification
- **Performance Metrics**:
  - Accuracy ~86%
  - F1-score for both classes ~85–87%
  - Confusion matrix and classification report used for evaluation

---

## 📊 Sample Results
          precision    recall  f1-score   support

       0       0.84      0.88      0.86     
       1       0.89      0.85      0.87     

accuracy                           0.86     

---

## 📌 Future Improvements

- Replace heuristics with human-annotated or crowdsourced labels
- Use transformer-based models (e.g., BERT) for better semantic understanding
- Build and deploy a web app for real-time review validation

---

## 🗂️ Repository Contents


---

## 👤 Author

**Muhammad Ghulam Ali**  
MS Business Analytics | Machine Learning Practitioner  
📧 [mghulamali888@gmail.com](mailto:mghulamali888@gmail.com)  
🔗 [GitHub](https://github.com/Muhammad-Ghulam-Ali)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).


