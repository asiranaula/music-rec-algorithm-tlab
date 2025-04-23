# 🎵 Music Recommendation Algorithm – TLAB Project

## Project Summary
This project uses machine learning techniques to cluster listener's musical preferences in order to recommend personalized song suggestions. The model was built as part of a TLAB research initiative focused on understanding music consumption through unsupervised learning.

## Features
- Clusters user profiles based on numerical and behavioral features
- Automatically detects and flags outliers in user sentiment data
- Recommends songs based on nearest-cluster matching
- Includes a visualization of cluster distribution using PCA
- Scalable to larger datasets

## Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn (KMeans, PCA, t-SNE)
- Matplotlib, Seaborn
- Jupyter Notebook / VS Code

## Clustering Methodology
The following steps were applied to build and evaluate the clustering model:

1. **Data Preprocessing**: Cleaned the dataset, handled missing values, and identified outliers based on IQR.
2. **Feature Scaling**: Used `StandardScaler` to normalize numeric columns.
3. **Model Training**: Trained a `KMeans` clustering algorithm on the scaled features.
4. **Cluster Prediction**: Assigned a test dataset to the nearest trained clusters.
5. **Model Evaluation**: Visualized results and evaluated the cohesion of cluster assignments.


---

## 📝 Report

# (1) EDA Insights
During the exploratory data analysis (EDA), there were several important insights that stood out:

- Most songs in this dataset are not wordy- the average length of a song was almost 75 words. 
- Sadness, Violence, and World/Life themes were the most prominent across all genres.
- Pop, Blues, and Jazz have maintained steady popularity over time.
- A high negative correlation between Age and Release Date suggest that this dataset consists of mostly modern music and themes. 

 Notably, features such as length of a song (by words per lyrics), genre, and feelings showed meaningful correlations. For example, although correlation values were generally low—as is typical in emotionally subjective datasets—there were consistent, interpretable trends:

- Feelings had a weak-to-moderate positive correlation with length (0.30) and dating (0.26), suggesting an overlap between emotional/thoughtful lyrics and romantic content.
- Emotionally impactful songs tend to be relational, personal, and feeling-driven, while less emotional songs are more likely to focus on external themes or be more observational than expressive.

# (2) Feature Selection Process
- The EDA helped guide the decision to keep or remove certain features. 
- Columns that were identifiers (like song title or artist name) or those that provided little variance were excluded from clustering. 
- The goal was to retain only the numerical features that contributed meaningful variance across tracks, ensuring the clustering was based on similar musical characteristics.

# (3) Choosing the Number of Clusters
- The Elbow Method was applied to visualize the relationship between the number of clusters and the within-cluster sum of squares (WCSS). This revealed that a value of k = 3 was ideal, as it showed a clear “elbow” where adding more clusters no longer significantly reduced WCSS. 
- This choice was further supported by cluster visualizations using PCA.

# (4) Cluster Interpretation
Once the clustering model was trained, each cluster exhibited distinct musical traits:

- One cluster consisted of acoustic and calming songs that were shorter in length, likely representing easy listening or folk-style music. 
- Another cluster leaned toward high-energy and danceable tracks, capturing more tracks in the Pop and Rock genre. 
- A third cluster appeared to contain more instrumental or ambient music of longer lengths, suggesting moodier, possibly deeper-meaning content.

These groupings suggest that the algorithm successfully picked up on emotional and structural patterns in the music.

# (5) Test Sample Recommendations
When applying the model to the test dataset, the songs were assigned into these predefined clusters. Since the test data was limited in size, most of the samples fell into a single cluster. However, based on their matching characteristics, specific songs from the training set were identified as recommendations. 
* I would recommend songs from Cluster 0 to this user, since those show higher rates of variables that correlate positively with this user: Violence, Dating, Communication, World/Life, and Night/Time.

---


