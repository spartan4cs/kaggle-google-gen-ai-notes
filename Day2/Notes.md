### 📚 **Resources**

* [Day 2 Livestream with Paige Bailey – 5-Day Gen AI Intensive Course  | Kaggle](https://www.youtube.com/watch?v=86GZC56rQCc&list=PLqFaTIg4myu-b1PlxitQdY0UYIbys-2es&index=3)
* [(217) Discord | #5dgai-q-and-a | Kaggle](https://discord.com/channels/1101210829807956100/1303438695143178251)

---

### **![🎒](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f392/32.png) Today’s Assignments**

Complete Unit 2: “Embeddings and Vector Stores/Databases”, which is:

* [Optional] Listen to the summary [podcast episode](https://www.youtube.com/watch?v=1CC39K76Nqs) for this unit (created by [NotebookLM](https://notebooklm.google.com/?original_referer=https:%2F%2Fwww.google.com%23&pli=1)).
* Read the [“Embeddings and Vector Stores/Databases” whitepaper](https://www.kaggle.com/whitepaper-embeddings-and-vector-stores).
* Complete these code labs on Kaggle:
  1. [Build](https://www.kaggle.com/code/markishere/day-2-document-q-a-with-rag) a RAG question-answering system over custom documents
  2. [Explore](https://www.kaggle.com/code/markishere/day-2-embeddings-and-similarity-scores) text similarity with embeddings
  3. [Build](https://www.kaggle.com/code/markishere/day-2-classifying-embeddings-with-keras) a neural classification network with Keras using embeddings

---

### **![💡](https://fonts.gstatic.com/s/e/notoemoji/15.1/1f4a1/32.png) What You’ll Learn**

Today you will learn about the conceptual underpinning of embeddings and vector databases and how they can be used to bring live or specialist data into your LLM application. You’ll also explore their geometrical powers for classifying and comparing textual data.

---

# ▶️ YT Notes Takeaways

Here are the **detailed notes for Day 2** of the Kaggle Generative AI Intensive Course, structured in markdown with examples for clarity. This session focuses on **Embeddings** and  **Vector Databases** .

---

# **Day 2: Kaggle Generative AI Intensive Course**

## **Overview**

* Day 2 explores:
  * **Embeddings** : Transforming data into numerical vectors that represent semantic meaning.
  * **Vector Databases** : Efficiently storing and retrieving embeddings for various applications.
* Activities include:
  * **Code Labs** : Hands-on tasks for building systems like document Q&A and similarity searches.
  * **Q&A Sessions** : Insights from experts on embeddings and vector databases.
  * **Pop Quiz** : Reinforcing concepts with review questions.

---

## **Key Topics**

### **1. Embeddings**

#### What are Embeddings?

* **Definition** : Numerical vectors that capture the semantic meaning of data (e.g., text, images, videos).
* **Purpose** : Represent complex data in a format suitable for machine learning tasks like:
* **Semantic Search**
* **Classification**
* **Recommendation Systems**

#### Types of Embeddings

1. **Text Embeddings** :

* Convert sentences or documents into vectors.
* Example:
  * Input: "The quick brown fox."
  * Output: A 512-dimensional vector.

1. **Multimodal Embeddings** :

* Handle inputs from multiple modalities (e.g., text + image).

1. **Graph and Structured Data Embeddings** :

* Represent relationships in structured formats like graphs.

#### Example

* **Similarity Check** :
* Sentence: "The quick brown fox."
* Similar Sentence: "A fast fox leaps."
* Semantic embeddings would place these close in vector space.

---

### **2. Vector Databases**

#### What are Vector Databases?

* Specialized storage solutions for managing embeddings.
* Key feature:  **Approximate Nearest Neighbor (ANN) Search** .
  * Efficiently finds vectors similar to a given query.

#### Advantages

* Handle billions of embeddings.
* Enable semantic searches at scale.

#### Algorithms for Vector Search

1. **Hierarchical Navigable Small World (HNSW)** :

* Graph-based approach for ANN search.

1. **SCAN Algorithm** :

* Used in Google services like Search, Ads, and YouTube.
* Excels in high-dimensional data with speed-accuracy trade-offs.

---

### **3. Retrieval Augmented Generation (RAG)**

#### What is RAG?

* Combines embeddings and vector databases to enhance LLM outputs.
* **Steps** :

1. **Embedding and Indexing** :
   * Convert documents into embeddings and store them in a database.
2. **Retrieval** :
   * Find the most relevant documents using ANN search.
3. **Generation** :
   * Use retrieved documents as context for LLM responses.

#### Benefits

* Overcomes limitations of static LLMs (e.g., outdated training data).
* Reduces hallucinations by providing accurate context.

---

## **Day 2 Code Labs**

### **1. Document Q&A System**

* **Objective** : Build a RAG-based system using **ChromaDB** and Gemini APIs.
* **Process** :

1. **Document Embedding** :
   * Create embeddings for documents using text embedding models.
   * Example:

   ```python
   embedding = generate_embedding("This is a sample document.")
   ```
2. **Query Embedding** :
   * Embed user queries to find similar documents.
3. **Semantic Search** :
   * Retrieve relevant documents using ANN search.
4. **Response Generation** :
   * Provide retrieved context to an LLM for answering questions.

#### Example Workflow

* **Input** :
* Documents: ["AI is evolving.", "Machine learning is powerful."]
* Query: "What is AI?"
* **Output** :
* Retrieved Document: "AI is evolving."
* Answer: "AI stands for Artificial Intelligence and is rapidly evolving."

---

### **2. Semantic Similarity Heatmap**

* **Objective** : Visualize semantic similarity between text documents.
* **Steps** :

1. Define sample texts.
   ```python
   texts = ["The quick brown fox.", "A fast fox jumps."]
   ```
2. Generate embeddings for all texts.
3. Compute pairwise similarities and plot as a heatmap.

#### Example Heatmap

* **Rows and Columns** : Text documents.
* **Values** : Similarity scores (lighter colors = higher similarity).

---

### **3. Embeddings for Classification**

* **Objective** : Use embeddings as input for classification tasks.
* **Steps** :

1. Generate embeddings for labeled text data.
2. Train a simple model (e.g., Keras Dense Layer) using embeddings as input.
3. Test the model on unseen data.

#### Example

* **Task** : Classify news articles by topic.
* Topics: Sports, Politics, Technology.
* **Approach** :
* Pre-trained embeddings simplify the task, requiring less training data.

---

## **Q&A Highlights**

1. **What are Embeddings Used For?**
   * Semantic Search.
   * Recommendation Systems.
   * Classification and Ranking.
2. **What are Vector Databases?**
   * Efficient storage and retrieval systems for embeddings.
   * Examples: ChromaDB, PostgreSQL (with PGVector).
3. **How to Combine RAG with LLMs?**
   * Use vector databases for retrieval.
   * Provide retrieved documents as context to LLMs.
4. **What Happens if Retrieval Fails?**
   * Use agent-based systems for multi-step reasoning and dynamic retrieval.

---

## **Pop Quiz Questions**

1. **What modalities can be converted into embeddings?**
   * **Answer** : Text, Image, Video, Audio (all of the above).
2. **What is the major advantage of SCAN?**
   * **Answer** : Speed-accuracy trade-offs for high-dimensional data.
3. **What is a key weakness of Bag-of-Words models?**
   * **Answer** : Ignores word ordering and semantic meaning.
4. **How to address embeddings not capturing literal information?**
   * **Answer** : Combine embeddings with full-text search.
5. **What is the advantage of locality-sensitive hashing?**
   * **Answer** : Reduces search space by grouping similar items.

---
