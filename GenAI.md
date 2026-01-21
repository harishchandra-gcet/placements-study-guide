© 2026 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# Generative AI Topics

## 1. Foundations of Generative AI & LLMs

Generative AI refers to a class of AI models capable of creating new content (text, images, code) rather than just classifying or predicting existing data.

### Large Language Models (LLMs)

LLMs are deep learning models trained on massive datasets (petabytes of text) to understand and generate human-like language. They are primarily based on the **Transformer architecture**.

* **GPT (Generative Pre-trained Transformer):** Created by OpenAI. It is a **decoder-only** model designed for autoregressive text generation (predicting the next word in a sequence).
* **LLaMA (Large Language Model Meta AI):** An open-source collection of foundation models. It is highly efficient and serves as the "base" for many specialized models in the community.
* **Mistral:** Known for efficiency. It utilizes **Sliding Window Attention** and **Mixture of Experts (MoE)**, allowing it to handle long contexts with fewer computational resources than GPT-4.

### How they work (Simplified)

Most LLMs use the **Self-Attention mechanism**. This allows the model to weigh the importance of different words in a sentence regardless of their distance from each other. For example, in the sentence *"The bank of the river was muddy,"* the model uses attention to link "bank" with "river" rather than "money."



## 2. Model Optimization: Fine-tuning vs. RAG

This is the most common interview topic. Companies want to know how you would adapt a general model to a specific business use case.

### Retrieval-Augmented Generation (RAG)

RAG provides the model with access to external, real-time data without changing the model's weights. It "looks up" information in a private database before generating an answer.

* **Best for:** Accuracy, citing sources, and handling frequently changing data (e.g., current stock prices or company HR policies).

### Fine-Tuning

Fine-tuning involves training the model further on a smaller, domain-specific dataset to change its behavior or style.

* **PEFT/LoRA:** Modern fine-tuning often uses **Parameter-Efficient Fine-Tuning (PEFT)** or **Low-Rank Adaptation (LoRA)**, which updates only a tiny fraction of the model’s weights, making it much faster and cheaper.
* **Best for:** Specific tones, specialized formats (like medical coding), or learning a specific dialect/jargon.

### Comparison Table

| Feature | RAG | Fine-Tuning |
| --- | --- | --- |
| **Knowledge Update** | Easy (just update the database) | Hard (requires retraining) |
| **Hallucination** | Low (uses grounded facts) | Higher (relies on memory) |
| **Cost** | Lower (Infra + Vector DB) | Higher (Compute + GPU time) |
| **Use Case** | Fact-based queries | Style/Domain adaptation |



## 3. Prompt Engineering Basics

Prompt engineering is the art of crafting inputs to get the most accurate or creative output from an LLM.

* **Zero-shot Prompting:** Asking a question without examples (e.g., "Translate this to French: Hello").
* **Few-shot Prompting:** Providing 2–3 examples within the prompt to guide the model's style.
* **Chain-of-Thought (CoT):** Asking the model to "think step-by-step." This significantly improves performance on logic and math problems.
* **System Prompts:** Setting the "persona" (e.g., "You are a senior Python developer").



## 4. Text Generation & Summarization

### Text Generation

LLMs generate text **token by token**. A token is roughly 4 characters or 0.75 words. The model calculates the probability of the next token and selects one based on parameters like:

* **Temperature:** High temperature (e.g., 0.8) makes output creative/random; low temperature (e.g., 0.2) makes it focused and deterministic.

### Summarization

There are two main types of AI summarization:

1. **Extractive:** Pulling out the most important sentences directly from the text (older method).
2. **Abstractive:** Understanding the context and writing a new, original summary (LLMs do this).



## 5. Vision Foundational Models

Generative AI isn't just for text. Foundational models in vision have changed how we create and understand images.

* **Stable Diffusion:** A **Diffusion Model**. It works by adding Gaussian noise to an image until it’s unrecognizable, then learning to "denoise" it back into a clear image based on a text prompt.
* **CLIP (Contrastive Language-Image Pre-training):** Developed by OpenAI, it bridges the gap between text and images. It learns which text descriptions go with which images, enabling "Text-to-Image" capabilities.
* **Multimodal Models:** Models like GPT-4o or Gemini that can process both text and images simultaneously (e.g., "Look at this photo of a broken pipe and tell me how to fix it").

## 6. Attention Mechanism in Transformers

The **Attention Mechanism** is the "brain" of the Transformer architecture. Before it was invented, AI models (like RNNs and LSTMs) processed text word-by-word, often "forgetting" the beginning of a sentence by the time they reached the end.

Attention allows the model to look at **every word in a sentence simultaneously** and decide which ones are most relevant to the word it is currently processing.


### Self-Attention

Self-attention allows a model to create a "map" of how words in a single sequence relate to one another.

* **Example:** "The **animal** didn't cross the **street** because **it** was too tired."
* **How Attention Works:** When the model processes the word "**it**," the attention mechanism assigns a high "weight" to "**animal**" and a lower weight to "**street**." This tells the model that "it" refers to the animal.



### Query, Key, and Value (QKV)

To calculate attention, the model transforms each word's input vector into three distinct vectors. Think of this like a **Library Search System**:

1. **Query ():** This represents the "search term" or the current word looking for context. ("I am the word 'it', what else should I care about?")
2. **Key ():** This represents the "label" or index of every word in the sequence. It tells the query how much information it has to offer.
3. **Value ():** This is the actual "content" or information that is passed along once a match between Q and K is found.

#### The Mathematical Formula

The standard calculation used in Transformers is **Scaled Dot-Product Attention**:

* **:** The dot product of the Query and Key determines the "compatibility score" (how much focus to put on other words).
* ** (Scaling):** We divide by the square root of the dimension of the keys to keep the gradients stable during training.
* **Softmax:** This turns the scores into probabilities that sum to 1 (weights).
* **Multiplying by :** This keeps the information from the most relevant words and filters out the irrelevant ones.


### Multi-Head Attention

Instead of performing the attention calculation once, Transformers do it several times in parallel. Each of these parallel calculations is called a **"Head."**

* **Why?** Different heads can learn different types of relationships.
* **Head 1** might focus on grammar (subject-verb agreement).
* **Head 2** might focus on entities (names, places).
* **Head 3** might focus on the emotional tone of the sentence.


* The results of all heads are concatenated and transformed back into the original dimension.



### Why it Matters for Interviews

In an interview, you should be able to explain the advantages of Attention over older architectures:

* **Parallelization:** Unlike RNNs, which must wait for the previous word to finish, Attention processes all words at once. This allows for training on massive GPUs.
* **Global Context:** Attention can capture relationships between words that are 1,000 words apart just as easily as words that are next to each other.
* **Explainability:** By looking at the attention weights (the "heatmap"), we can actually see *why* a model made a specific prediction.


## Interview Drill: Expected Questions & Answers

### Q1: What is a Large Language Model (LLM)?

**Answer:** An LLM is a type of artificial intelligence trained on vast amounts of text data to understand, summarize, and generate human language. It is typically based on the Transformer architecture and uses self-attention mechanisms to understand the relationship between words in a sequence. Examples include GPT-4, LLaMA, and Mistral.

### Q2: What is the difference between Fine-tuning and RAG?

**Answer:** Fine-tuning involves retraining the model's weights on a specific dataset to change its behavior or internal knowledge. RAG (Retrieval-Augmented Generation) does not change the model; instead, it retrieves relevant documents from an external database and provides them to the model as context to answer a specific query. RAG is better for factual accuracy, while fine-tuning is better for specialized style/format.

### Q3: How does a Diffusion Model (like Stable Diffusion) work?

**Answer:** It works through a two-step process: **Forward Diffusion**, where noise is gradually added to an image until it becomes pure static, and **Reverse Diffusion**, where the model is trained to remove that noise step-by-step to recover or generate a new image based on a text prompt.

### Q4: What is "Hallucination" in LLMs and how do you prevent it?

**Answer:** Hallucination is when an LLM generates factually incorrect but confident-sounding information. It happens because LLMs predict the "most likely" next word, not necessarily the "truth." We can mitigate this using **RAG** (grounding the model in facts), **lowering the Temperature** setting, or using **Chain-of-Thought prompting**.


### Q5: Why do we use "Scaling" () in the attention formula?

**Answer:** Without scaling, the dot product of  and  can grow very large in magnitude for high-dimensional vectors. This pushes the softmax function into regions where the gradient is extremely small (the "vanishing gradient" problem), making the model nearly impossible to train. Scaling keeps the values in a manageable range.

### Q6: What is the difference between Self-Attention and Cross-Attention?

**Answer:** * **Self-Attention:** The Queries, Keys, and Values all come from the same sequence (e.g., an LLM reading a sentence).

* **Cross-Attention:** The Queries come from one sequence (e.g., the decoder in a translator), but the Keys and Values come from a *different* sequence (e.g., the encoder's original language input). This is how translation models "look" at the source language while writing the target language.

### Q7: What is the time complexity of the standard Self-Attention mechanism?

**Answer:** The complexity is ****, where  is the sequence length. This is because every word must be compared against every other word in the sequence. This "quadratic bottleneck" is why long-context windows (like 100k+ tokens) are computationally expensive.
