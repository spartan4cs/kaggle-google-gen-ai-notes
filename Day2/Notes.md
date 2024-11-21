### 📚 Resources

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

## Kaggle Generative AI Intensive Course - Day 2 Notes

## Overview

- **Topic**: Embeddings and Vector Databases
- **Focus Areas**:
  - Conceptual understanding of embeddings.
  - Using embeddings for downstream tasks.
  - Introduction to retrieval augmented generation (RAG).
  - Working with vector databases like ChromaDB.
- **Resources**:
  - Code labs for hands-on practice.
  - White papers for theory.
  - Q&A sessions with Google and DeepMind experts.

---

## Key Topics Covered

### 1. **Understanding Embeddings**

- **Definition**: Compact numerical representations of data (e.g., text, images, audio) capturing their semantic meaning.
- **Applications**:
  - Semantic similarity comparisons.
  - Clustering.
  - Classification.
  - Recommendation systems.
  - Retrieval-augmented generation (RAG).
- **Types**:
  - **Text Embeddings**: Numerical vectors representing semantic relationships between words or sentences.
  - **Multimodal Embeddings**: Combine data types such as images, audio, and video.

---

### 2. **Vector Databases**

- **Purpose**: Store and manage embeddings for quick retrieval based on similarity.
- **Search Techniques**:
  - **Exact Nearest Neighbor Search**: Computes the distance between the query and all stored embeddings.
  - **Approximate Nearest Neighbor (ANN) Search**:
    - **Graph-Based**: Hierarchical Navigable Small World (HNSW).
    - **Tree-Based**: Google’s SCaNN (Scalable Nearest Neighbor).
- **Advantages**:
  - Handles large datasets efficiently.
  - Fast retrieval for production-scale applications.

---

### 3. **RAG (Retrieval-Augmented Generation)**

- **Purpose**: Mitigate the limitations of LLMs by retrieving relevant information dynamically. Keeping thhe model updated with relavant information, so when we query it will give latest information rather than stale information.
- **Process**:
  1. **Embedding & Indexing**:
     - Convert documents and queries into embeddings.
     - Index embeddings in a vector database.
  2. **Retrieval**:
     - Retrieve top-k relevant documents based on similarity.
  3. **Generation**:
     - Use retrieved documents as context in the prompt for the LLM.
- **Benefits**:
  - Reduces hallucinations in LLM responses.
  - Provides accurate and context-aware answers.

---

## Code Labs Overview

### 1. **Building a RAG System with ChromaDB**

- **Objective**: Create a document Q&A system using embeddings and vector databases.
- **Steps**:
  1. Install necessary libraries and initialize the embedding model.
  2. Create a small dataset and embed it using the Gemini text embedding API.
  3. Index embeddings in ChromaDB.
  4. Query ChromaDB to retrieve the most relevant documents.
  5. Use the retrieved documents as context for LLM responses.

---

### 2. **Understanding Semantic Similarity**

- **Objective**: Compare semantic similarity between different text documents using embeddings.
- **Steps**:
  1. Initialize the Gemini API and define sample text documents.
  2. Compute embeddings for each document.
  3. Generate a similarity matrix and visualize it as a heat map.
  4. Analyze relationships between documents based on semantic similarity.

---

### 3. **Using Embeddings for Classification**

- **Objective**: Use pre-trained embeddings to classify News Group posts with a simple Keras model.
- **Steps**:
  1. Preprocess the News Group dataset.
  2. Split the dataset into training and testing sets.
  3. Generate embeddings for each post using the Gemini embedding API.
  4. Train a dense classification model using embeddings as input.
  5. Evaluate performance, achieving high accuracy with limited data.

---

## Q&A Highlights

### 1. **What are embeddings and why are they useful?**

- **Embeddings**: Numerical representations of data capturing semantic relationships.
- **Applications**:
  - Recommendation systems.
  - Semantic search.
  - Classification tasks.

### 2. **What are the trade-offs between open-source and proprietary vector databases?**

- **Open Source**:
  - Pros: Cost-effective, flexible, customizable.
  - Cons: Higher maintenance and complexity.
- **Proprietary**:
  - Pros: Managed services, ease of use, stability.
  - Cons: Costly, vendor lock-in.

### **3. Do you think new features and capabilities like Gemini's longer context windows and Google's recently released search grounding will reduce the need for vector databases?**

* **Answer**: No, they are complementary
* **Longer context windows** allow for more relevant data in the LLM prompt.
* **Vector databases** efficiently retrieve the most relevant data from large datasets.

### 4. **How can we train embedding models from decoder-only backbones?**

- Start with decoder-only LLMs.
- Fine-tune for bidirectional attention to improve embedding quality.

### 5. **What if RAG retrieves irrelevant documents?**

- Solutions:
  - Fine-tune embedding models for better relevance.
  - Use agent-based systems for dynamic retrieval steps.
  - Combine multiple tools and techniques (e.g., search grounding).

---

## Pop Quiz Questions and Answers

### Question 1: What modalities can be converted into embeddings?

- **Answer**: D) All of the above (text, image, video, audio).

### Question 2: Major advantage of SCaNN over other ANN algorithms?

- **Answer**: B) Designed for high-dimensional data with excellent speed-accuracy trade-offs.

### Question 3: Weakness of bag-of-words models?

- **Answer**: A) Ignore word ordering and semantic meaning.

### Question 4: How to address embeddings’ limitations for search?

- **Answer**: C) Combine embeddings with full-text search for better literal information capture.

### Question 5: Primary advantage of locality-sensitive hashing (LSH)?

- **Answer**: B) Reduces the search space by grouping similar items into hash buckets.

---

## Key Takeaways

- **Embeddings**:
  - Represent data semantically and compactly.
  - Useful for semantic search, classification, and clustering.
- **Vector Databases**:
  - Efficiently manage and retrieve embeddings at scale.
  - Complement LLMs for dynamic and accurate applications.
- **RAG**:
  - Enhances LLM performance by grounding responses in relevant, retrieved data.

---

Let me know if you need more details or sections expanded!
