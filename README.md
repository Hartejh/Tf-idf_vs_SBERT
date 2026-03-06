## TF-IDF vs SBERT Text Classification

This project compares two text representations for supervised news topic classification: **TF-IDF vectors** and **SBERT sentence embeddings**. Using a dataset of 153 unique news headlines across four topics (Healthcare, Animals, Sports – Football, and Transportation), Random Forest classifiers were trained on both feature types. The goal was to evaluate how sparse word-based representations compare to dense contextual embeddings for short-text classification.

After preprocessing the text using tokenization, stopword removal, punctuation filtering, and lemmatization, TF-IDF produced a **153 × 957 document-term matrix**, while SBERT generated **384-dimensional sentence embeddings** using the `all-MiniLM-L6-v2` model. Models were tuned using **5-fold cross-validation**, and class imbalance was addressed using **RandomOverSampler** within each fold.

The **SBERT representation significantly outperformed TF-IDF**, achieving:

- **SBERT Random Forest**
  - Test Accuracy: **90.3%**
  - Macro F1: **0.88**
  - Cross-Validation Macro F1: **0.919**

- **TF-IDF Random Forest**
  - Test Accuracy: **70.9%**
  - Macro F1: **0.68**
  - Cross-Validation Macro F1: **0.704**

These results highlight the advantage of **context-aware sentence embeddings**, which capture semantic relationships between words more effectively than sparse bag-of-words features, particularly in short text and imbalanced datasets.

Full report:  
[TF-IDF vs SBERT Analysis](https://docs.google.com/document/d/10jEPEfwemtGgKR58U7dRmUCh-v_ed7rJEozzsGZFC88/edit)
