
## 🧠 Drug Reviews NLP & Clustering Analysis

Turning unstructured patient reviews into actionable healthcare insights using NLP and Machine Learning.

📌 **Overview**

This project applies Natural Language Processing (NLP) and unsupervised machine learning to analyze patient drug reviews, with the goal of uncovering patterns in treatment effectiveness and side-effect experiences.

Using text data from patient reviews, the analysis identifies clusters of treatment experiences and evaluates whether patients form distinct groups or a continuous spectrum.

🎯 **Objectives**

- Transform unstructured text into meaningful numerical features
- Identify patient segments using clustering
- Analyze relationships between effectiveness, side effects, and satisfaction
- Provide interpretable, data-driven insights

🗂️ **Dataset**

- Source: UCI Drug Reviews Dataset
- Features used:
    - Review text
    - Effectiveness
    - Side effects
    - Ratings

🧰 **Methodology**

1. Text Preprocessing

    - Lowercasing and noise removal
    - Stopword filtering (standard + domain-specific + drug names)
    - Phrase normalization (e.g., side_effects, no_side_effects)
    - Lemmatization (converting words to their base)

2. Feature Engineering

    - TF-IDF Vectorization (unigrams + bigrams)
    - Captures important medical phrases (e.g., “abdominal pain”, “acid reflux”)

3. Dimensionality Reduction

    - Truncated SVD applied to reduce high-dimensional sparse features
    - Preserves key semantic structure while improving computational efficiency

4. Clustering

    - K-Means Clustering applied on reduced feature space
    - Tested multiple values of k using:
        1. Elbow Method
        2. Silhouette Score

5. Cluster Profiling

    Clusters were analyzed based on:

    - Effectiveness levels
    - Side-effect severity
    - Patient ratings

📊 **Model Selection Insights**

- SVD
    - No clear variance elbow (typical for NLP)
    - ~40% variance captured at ~68 components
    - Optimal performance at 80 components

- Clustering
    - No sharp elbow in inertia curve
    - Silhouette scores (~0.12) reflect overlapping text data
    - k = 2–3 provides best balance between performance and interpretability

🔍 **Results**

🧩 **Cluster Segmentation**

- Cluster 1 – Dermatological Effects
    - Keywords: dry, skin, peeling, redness
    - Characteristics:
        1. Localized side effects
        2. Mild to moderate severity
        3. Average rating: 7.1

- Cluster 2 – Systemic Effects
    - Keywords: nausea, headache, fatigue, pain
    - Characteristics:
        1. Whole-body impact
        2. Lower severity (higher percentage of respondents with no or mild side effects)
        3. Average rating: 6.9 

🧠 **Key Insights**

Patient experiences naturally segment into localized (dermatological side effects) vs systemic side effects (nausea, headache, etc.), providing meaningful clinical interpretation despite modest clustering scores.

📈 **Visualizations**

- 📉 Elbow vs Silhouette combined chart
- ☁️ Word clouds per cluster
- 📊 Effectiveness vs Side Effects distribution

🧠 **Key Learnings**

- Text data is high-dimensional and noisy
- Maximizing variance does not improve clustering
- Interpretability is as important as performance
- Combining metrics leads to better decisions

💼 **Business Impact**

- Enables patient segmentation
- Supports:
    - Treatment personalization
    - Risk assessment
    - Improved adherence strategies

🛠️ **Tech Stack**

- Python
- Pandas/NumPy
- Scikit-learn
- NLP (TF-IDF, SVD)
- Matplotlib/Seaborn