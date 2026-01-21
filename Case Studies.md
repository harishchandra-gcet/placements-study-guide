© 2026 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# Case Studies

Each section follows a **Standard ML Lifecycle** format: Data  Preprocessing  Modeling  Evaluation.

## 1. Case Study: Predicting Customer Churn

**Objective:** Predict which customers are likely to leave a service based on their historical behavior.

### A. Data Preparation & Feature Engineering

* **Key Features:** Tenure (how long they’ve been a customer), monthly charges, contract type, technical support usage, and payment method.
* **The "Target" Variable:** Usually binary ( for Churn,  for Retained).
* **Data Leakage (Critical Interview Point):** Ensure you don't include "future" features like "Date of cancellation" or "Last login date" if that date is after the churn event.

### B. Handling Imbalance

Churn datasets are almost always imbalanced (fewer people leave than stay).

* **Upsampling (SMOTE):** Creating synthetic examples of the minority class.
* **Downsampling:** Reducing the majority class samples.
* **Class Weights:** Telling the algorithm (e.g., XGBoost) to penalize errors on the "Churn" class more heavily.

### C. Modeling & Evaluation

* **Algorithms:** Random Forest or XGBoost are standard because they handle non-linear relationships and missing values well.
* **Metrics:** * **Recall:** Crucial here. We would rather falsely flag a customer as "likely to churn" (and give them a discount) than miss a customer who actually leaves.
* **AUC-ROC:** Measures how well the model distinguishes between classes.



> **Interview Question:** "If your model has 95% accuracy but the churn rate is only 5%, is your model good?"
> **Answer:** No. A "dumb" model that predicts "No Churn" for everyone would also get 95% accuracy but 0% recall. We need to look at the **F1-Score** and **Precision-Recall Curve**.



## 2. Case Study: Sentiment Classifier for Product Reviews

**Objective:** Classify text reviews as Positive, Negative, or Neutral.

### A. NLP Preprocessing Pipeline

1. **Lowercasing & Cleaning:** Removing HTML tags, punctuation, and special characters.
2. **Tokenization:** Breaking sentences into individual words.
3. **Stopword Removal:** Deleting common words like "the", "is", "at" that don't carry sentiment.
4. **Lemmatization:** Reducing words to their root form (e.g., "running"  "run").

### B. Text Vectorization

Computers can't read text; we must convert it to numbers:

* **TF-IDF:** Assigns weight to words based on how unique they are to a document.
* **Word Embeddings (Word2Vec/GloVe):** Captures semantic meaning (e.g., "King" and "Queen" are mathematically close).

### C. Modeling

* **Baseline:** Naive Bayes (fast, works well for small data).
* **Advanced:** BERT (Bidirectional Encoder Representations from Transformers). BERT understands context (e.g., the word "bank" in "river bank" vs "money bank").



## 3. Case Study: CNN for Image Classification (Damaged vs. Non-Damaged)

**Objective:** Use Computer Vision to identify defects in items (e.g., on a manufacturing line).

### A. The CNN Architecture

Explain the layers in order:

1. **Convolutional Layer:** Uses filters to detect features (edges, textures, shapes).
2. **ReLU Activation:** Introduces non-linearity so the model can learn complex patterns.
3. **Pooling (Max Pooling):** Reduces the spatial size (dimensions) of the data to speed up computation and reduce overfitting.
4. **Fully Connected (Dense) Layer:** Performs the final classification based on features extracted.

### B. Transfer Learning (The "Pro" Answer)

Instead of training from scratch, use a pre-trained model like **ResNet** or **MobileNet** (trained on ImageNet).

* **Why?** These models already know how to "see" shapes/edges. You only need to "fine-tune" the last layer for your specific "Damage" vs "No Damage" task.

### C. Data Augmentation

Since "damaged" items might be rare, use augmentation:

* **Flips, Rotations, Zooming:** Creates "new" images from existing ones to make the model robust to different angles/lighting.



## 4. Case Study: Small LLM for Document Summarization

**Objective:** Use a resource-efficient Large Language Model to condense long text.

### A. Why "Small" LLMs?

In production, we often use models like **DistilBART**, **T5-Small**, or **TinyLlama** because they are faster and cheaper than GPT-4.

### B. The Summarization Approach

* **Extractive:** Selecting the most important sentences directly from the text.
* **Abstractive (Better):** The model "re-writes" the summary in its own words (like a human).

### C. Evaluation Metrics (ROUGE)

* **ROUGE Score:** Compares the model's summary to a human reference. It looks for overlapping words (N-grams).

### D. Optimizing for "Long" Documents

* **Challenge:** LLMs have a "Context Window" limit (e.g., 4096 tokens).
* **Solution:** **"Map-Reduce" strategy.** Break the document into chunks, summarize each chunk, and then summarize the summaries.



## Summary Table: Interview Quick-Ref

| Task | Key Challenge | Best Metric | Winning Model/Approach |
| --- | --- | --- | --- |
| **Churn** | Imbalanced Data | Recall / F1-Score | XGBoost + SMOTE |
| **Sentiment** | Context/Sarcasm | Accuracy / F1 | BERT / Transformers |
| **Damage (CV)** | Limited Data | Precision (no false alarms) | CNN + Transfer Learning |
| **Summarization** | Long Text Lengths | ROUGE Score | T5 / DistilBART (Quantized) |



### Final Technical Tips

* **Explainability:** If they ask how to explain a model's decision, mention **SHAP** or **LIME** (they show which feature, like "Price," most influenced a prediction).
* **Deployment:** Mention that you would package these models using **Flask** or **FastAPI** and containerize them with **Docker**.
* **Quantization:** For "Small LLMs," mention **4-bit quantization** (making the model smaller by reducing the precision of its weights).
