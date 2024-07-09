# Personalized Recommender System for Online Courses
I have completed this project as a part of the Machine Learning Professional Certification by IBM. The project mainly includes three parts: <br />
1) Exploratory Data Analysis
2) Content Based FIltering
3) Collaborative Filtering

## Exploratory Data Analysis:
Word Cloud:<br /> ![a9df0faf-cdbd-4c6f-8651-0f6529b95287](https://github.com/darKKnight14110/Recommender_System/assets/142472592/8a9211e0-3680-4444-9842-c9e11ba8f906) <br />
Enrollment Distribution:<br /> ![84f5360d-65bd-4903-b1d8-e17e10ce6c22](https://github.com/darKKnight14110/Recommender_System/assets/142472592/d68ed356-e06b-4e94-9de3-796c87267dc7)  <br />
Top 20 Courses:<br /> ![image](https://github.com/darKKnight14110/Recommender_System/assets/142472592/5de968a7-773b-4a1d-9141-a65892c05852) <br />

## Content Based Filtering:
### 1) User Profile Based: 
Explanation: <br />
Content-based recommender systems leverage the inherent characteristics of users and courses to suggest similar items. This approach assumes users who enjoyed specific content in the past are likely to appreciate similar content in the future.
User Profiles: These represent user preferences based on their past interactions (ratings, clicks, enrollments). 
Course Genres: Categories that classify courses based on subject matter (e.g., Programming, Data Science, Design). <br />
Approach: <br />
We represent the User Profile by using a matrix which has the user’s rating for certain courses. Now we provide to represent the Course genres by using a matrix of 0s and 1s explaining if a course is of a particular domain or not. Taking a dot product of the two matrices enables us to generate a recommender system for that particular user. <br />

### 2) Course Similarity Based
Explanation:<br />
Course similarity identifies courses with characteristics similar to those a user has previously enjoyed. This allows the system to recommend content that aligns with the user's learning path. Several techniques can be used to calculate course similarity<br />
Approach:<br />
Keyword Matching: This approach identifies keywords present in course descriptions, titles, or learning objectives. Courses with a high overlap in keywords are considered similar and recommended to the user. Each course title can be broken into words and similarity among the words denotes the course similarity<br />

### 3) Clustering Based
Explanation:<br />
User profile clustering groups users with similar interests and learning patterns. This allows the system to recommend courses popular within a user's cluster. By grouping users with similar profiles, the system can identify trends and suggest content that resonates with a specific segment of the user base.<br />
Approach:<br />
We use the clustering technique of KMeans Clustering with a grid search to find the optimal number of clusters. Then, we go on to perform Principal Component Analysis(PCA) to reduce the number of features. Now we re-perform KMeans Clustering and compare the accuracy.<br />

## Colaborative Filtering:
### 1) K Nearest Neighbours based
Explanation: <br />
KNN (K-Nearest Neighbors) is a collaborative filtering technique that recommends items based on the preferences of similar users. Here's how it works: <br />
User Similarity: The system calculates the similarity between the user seeking recommendations and other users in the dataset. This similarity can be measured using various metrics like cosine similarity or Pearson correlation. These metrics consider the users' ratings or interactions with different courses. <br />
K-Nearest Neighbors: A predefined number of most similar users (K) are identified as the user's nearest neighbors. These neighbors are the users with the highest similarity scores in step 1. <br />
Recommendation Generation: The system analyzes the ratings or interactions of the K nearest neighbors for courses the target user hasn't interacted with. Courses with high ratings or positive interactions from the neighbors are then recommended to the target user.<br />

### 2) Non-Negative Matrix Factorization based
Non-Negative Matrix Factorization (NMF) is a dimensionality reduction technique used for collaborative filtering. It addresses the sparsity issue in recommendation systems, where most users only interact with a small fraction of all available courses.<br />
Sparse Rating Matrix: Imagine a matrix where rows represent users and columns represent courses. Each cell contains a rating or interaction value (e.g., 1 for enrolled, 0 for not enrolled). This matrix is often sparse, with many empty cells due to users not interacting with most courses.<br />
NMF Decomposition: NMF decomposes the user-item rating matrix into two lower-dimensional matrices. One matrix represents latent factors associated with users (e.g., interest in web development, data science) and the other represents latent factors associated with courses (e.g., covers machine learning algorithms, uses Python programming).<br />
Recommendation Generation: By analyzing the user and course latent factors, the system can predict missing ratings or interactions. For a user with no interaction with a specific course, NMF can estimate a potential rating based on the user's latent factors and the course's latent factors. Courses with high predicted ratings are then recommended.<br />

### 3) Neural Network Embedding Based
Neural networks are powerful tools for learning complex relationships between data points. In collaborative filtering, neural networks can be used to create embeddings for both users and courses. <br />
Embeddings: These are low-dimensional vector representations that capture the essential characteristics of users and courses. For users, the embedding might capture their interests, learning styles, or preferred course topics. For courses, the embedding might capture the subject matter, difficulty level, or required skills.<br />
Neural Network Training: The neural network is trained on the user-item interaction data (ratings, enrollments). During training, the network learns to map users and courses into similar embedding spaces based on their interactions.<br />
Recommendation Generation: Once trained, the network can predict the likelihood of a user interacting with a course based on the similarity between their respective embeddings. Courses with high predicted interaction scores are then recommended to the user.<br />

### Results:
#### Lowest RMSE Score: STACKING CLASSIFIER (0.09) <br />
This Stacking classifier comprised of: SVC, KNN and Decision Tree classifiers.
