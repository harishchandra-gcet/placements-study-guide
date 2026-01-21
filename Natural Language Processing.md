© 2026 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# Natural Language Processing  

## 1. Text Preprocessing

Before building models, raw text must be converted into a format the machine can understand.

* **Tokenization:** The process of breaking down a stream of text into smaller units called **tokens** (words, characters, or sub-words).
* **Stemming:** A rule-based process that chops off the ends of words to find the "root" form. It often results in non-dictionary words (e.g., "Studies" becomes "studi").
* **Lemmatization:** Uses vocabulary and morphological analysis to return the dictionary base form of a word, known as a **lemma** (e.g., "Better" becomes "Good").

### Stemming vs. Lemmatization

| Feature | Stemming | Lemmatization |
| --- | --- | --- |
| **Approach** | Heuristic/Rule-based | Linguistic Analysis |
| **Speed** | Very Fast | Slower (requires dictionary lookup) |
| **Accuracy** | Lower (crude chopping) | Higher (context-aware) |
| **Example** | "Caring"  "Car" | "Caring"  "Care" |



## 2. Vectorization: Bag-of-Words & TF-IDF

Machines cannot process strings; they need numbers.

### Bag-of-Words (BoW)

A representation of text that describes the occurrence of words within a document. It involves a vocabulary of known words and a measure of the presence of these words.

* **Drawback:** It loses word order and context (semantic meaning).

### TF-IDF (Term Frequency-Inverse Document Frequency)

TF-IDF reflects how important a word is to a document in a collection.

* **Term Frequency (TF):** Measures how frequently a term occurs in a document.


* **Inverse Document Frequency (IDF):** Measures how important a term is by weighing down common words (like "the", "is").





## 3. Word Embeddings

Unlike BoW or TF-IDF, which are "sparse" (mostly zeros), word embeddings are "dense" vectors where similar words have similar vector representations.

* **Word2Vec:** Developed by Google. It uses a shallow neural network to learn word associations.
* **CBOW (Continuous Bag of Words):** Predicts the target word based on context.
* **Skip-gram:** Predicts the surrounding context words based on a target word.


* **GloVe (Global Vectors):** Developed by Stanford. It focuses on the global co-occurrence statistics of words across the entire corpus, rather than local context windows like Word2Vec.



## 4. Sequence Models: LSTM & GRU

Standard Neural Networks cannot handle sequential data well because they lack "memory."

* **The Problem:** Traditional RNNs (Recurrent Neural Networks) suffer from the **Vanishing Gradient Problem**, making them unable to learn long-term dependencies.
* **LSTM (Long Short-Term Memory):** Introduces a "Cell State" and three gates (Forget, Input, Output) to regulate the flow of information. It decides what to keep and what to discard.
* **GRU (Gated Recurrent Unit):** A simplified version of LSTM. It merges the cell state and hidden state and uses only two gates (Reset and Update). It is computationally cheaper and often performs similarly to LSTM.



## 5. Transformers

Transformers revolutionized NLP by replacing recurrence with **Attention Mechanisms**.

* **Self-Attention:** Allows the model to look at other words in the input sequence to get a better encoding for a specific word. For example, in "The animal didn't cross the street because **it** was too tired," the attention mechanism helps the model associate "**it**" with "**animal**."
* **Parallelization:** Unlike RNNs, which process words one by one, Transformers process the entire sequence at once. This makes training significantly faster.



## 6. Evaluation Metrics

* **BLEU (Bilingual Evaluation Understudy):** Primarily used for Machine Translation. It calculates a score based on the overlap of n-grams between the machine-generated output and a reference translation. (Range: 0 to 1).
* **ROUGE (Recall-Oriented Understudy for Gisting Evaluation):** Primarily used for Text Summarization. It measures how much of the reference summary the machine-generated summary "covers" (Recall-focused).



## Example Interview Q&A

### Q1: What is TF-IDF?

**Answer:** TF-IDF stands for Term Frequency-Inverse Document Frequency. It is a statistical measure used to evaluate how relevant a word is to a document in a collection of documents.

* **TF** accounts for the frequency of a word in a specific document.
* **IDF** reduces the weight of words that occur very frequently across all documents (like "and", "the"), ensuring that unique, meaningful words get higher scores.
It is commonly used in Information Retrieval and Text Mining.

### Q2: Explain the idea behind word embeddings.

**Answer:** The core idea is **Semantic Proximity**. In traditional methods like One-Hot Encoding, words are treated as isolated entities with no relationship (the distance between "King" and "Queen" is the same as "King" and "Apple").
Word Embeddings map words into a high-dimensional continuous vector space. Words used in similar contexts are placed close to each other. This allows the model to capture relationships like synonyms, analogies (King - Man + Woman = Queen), and syntactic patterns.

### Q3: How do Transformers improve NLP tasks?

**Answer:** Transformers improve NLP in three main ways:

1. **Handling Long-term Dependencies:** Through the Self-Attention mechanism, they can link related words regardless of how far apart they are in a sentence.
2. **Parallel Processing:** Unlike RNNs/LSTMs that are sequential, Transformers process all words in a sentence simultaneously, which dramatically reduces training time.
3. **Non-directional context:** Models like BERT (based on Transformers) can read text bi-directionally, allowing the model to understand the full context of a word based on both its left and right neighbors.

