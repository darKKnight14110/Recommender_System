# Personalized Recommender System for Online Courses

## Project Overview
This project focuses on developing a **Personalized Recommender System** for online courses, leveraging both **Content-Based Filtering** and **Collaborative Filtering** techniques. The system is designed to help users find courses tailored to their preferences based on their past interactions and similarities with other users. 

The project was completed as part of the **Machine Learning Professional Certification** by IBM, and it incorporates the following key steps:
1. **Exploratory Data Analysis** (EDA)
2. **Content-Based Filtering**
3. **Collaborative Filtering**

## 1. Exploratory Data Analysis (EDA)
The first phase of the project involved analyzing the dataset to uncover insights into user behavior and course popularity.

### Visualizations:
- **Word Cloud of Course Descriptions**:  
  ![Word Cloud](https://github.com/darKKnight14110/Recommender_System/assets/142472592/8a9211e0-3680-4444-9842-c9e11ba8f906)
  
- **Enrollment Distribution**:  
  ![Enrollment Distribution](https://github.com/darKKnight14110/Recommender_System/assets/142472592/d68ed356-e06b-4e94-9de3-796c87267dc7)
  
- **Top 20 Courses by Enrollment**:  
  ![Top 20 Courses](https://github.com/darKKnight14110/Recommender_System/assets/142472592/5de968a7-773b-4a1d-9141-a65892c05852)

## 2. Content-Based Filtering
### A. **User Profile-Based Filtering**:
This method recommends courses based on a user’s historical preferences, comparing the user profile with course attributes such as genres (e.g., Programming, Data Science).

- **Approach**:  
  We represent user preferences as a matrix of user-course interactions and course genres as a matrix of categories (e.g., 0 or 1 for each domain). By calculating the dot product between these matrices, we generate personalized recommendations for users.

### B. **Course Similarity-Based Filtering**:
This approach identifies similar courses based on their content, helping users discover new courses related to ones they’ve already interacted with.

- **Approach**:  
  We use **keyword matching** to find overlap in course titles and descriptions. Courses with high keyword similarity are recommended to users.

### C. **Clustering-Based Filtering**:
Users are clustered based on their learning patterns and preferences to recommend popular courses within their cluster.

- **Approach**:  
  We applied **KMeans Clustering** with **PCA** for dimensionality reduction, followed by a grid search to optimize the number of clusters. This method helps identify user segments with similar preferences, enhancing recommendation accuracy.

## 3. Collaborative Filtering
### A. **K-Nearest Neighbors (KNN) Collaborative Filtering**:
KNN recommends courses based on the preferences of users with similar behavior.

- **Approach**:  
  The system calculates user similarity using metrics like **cosine similarity** or **Pearson correlation**, identifying the nearest neighbors and recommending courses that the neighbors rated highly but the target user hasn’t interacted with.

### B. **Non-Negative Matrix Factorization (NMF)**:
NMF is a dimensionality reduction technique used to fill in missing user-item interactions in sparse datasets.

- **Approach**:  
  NMF decomposes the user-course interaction matrix into two latent matrices. By analyzing these matrices, we predict ratings for courses a user hasn’t yet interacted with and recommend those with high predicted scores.

### C. **Neural Network Embedding**:
Deep learning-based embeddings capture complex relationships between users and courses to generate recommendations.

- **Approach**:  
  A neural network was trained on user-item interactions to learn embeddings for both users and courses. The model then predicts interactions based on embedding similarity, recommending courses with high likelihood scores.

## Results:
- **Best Performing Model**: Stacking Classifier with an RMSE score of **0.09**.
- **Stacking Classifier Components**: Support Vector Classifier (SVC), K-Nearest Neighbors (KNN), and Decision Tree Classifier.

## Conclusion:
This project successfully implemented multiple filtering techniques to build a robust recommender system for online courses. The system offers personalized course suggestions to users, enhancing their learning experience and helping them find courses aligned with their interests.

## Tools and Libraries:
- **Python**: Pandas, Scikit-learn, Matplotlib, Seaborn
- **ML Techniques**: Content-Based Filtering, Collaborative Filtering (KNN, NMF, Neural Networks), Stacking Classifier
- **Visualization**: PowerBI, Matplotlib, Seaborn

