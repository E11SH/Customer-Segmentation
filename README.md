# 🛍️ Customer Segmentation Analysis

This project performs an in-depth customer segmentation using unsupervised machine learning on the "Mall Customers" dataset. It leverages the K-Means algorithm to group customers into distinct, actionable segments based on their annual income and spending habits, providing a clear roadmap for targeted marketing strategies.

---

## 📌 Project Overview
- **Exploratory Data Analysis**: Loaded the dataset using Pandas, performed initial statistical analysis (`.describe()`), and visualized the raw data distribution with a scatter plot to identify potential groupings.
- **Feature Scaling**: Applied `StandardScaler` from Scikit-learn to normalize the 'Annual Income' and 'Spending Score' features, ensuring that the distance-based K-Means algorithm performs accurately without feature dominance.
- **Optimal Cluster Determination**: Implemented the **Elbow Method** by calculating the Within-Cluster Sum of Squares (WCSS) for a range of cluster numbers (1 to 10) to empirically identify the optimal number of clusters, which was found to be **five**.
- **K-Means Clustering**: Trained a K-Means model with $k=5$ to partition the customers into five distinct segments.
- **Segment Visualization**: Generated 2D scatter plots using Matplotlib and Seaborn to visualize the final clusters, clearly marking the centroids to highlight the center of each customer group.
- **Bonus Analysis**: Applied the **DBSCAN** algorithm as an alternative clustering method and performed a deeper analysis by calculating the average age, income, and spending score for each K-Means cluster.

---

## 🛠️ Tech Stack
- **Python**
- **Pandas** → Data loading, manipulation, and analysis
- **Scikit-learn** → Feature scaling and implementing clustering algorithms (K-Means, DBSCAN)
- **Matplotlib & Seaborn** → Data visualization and plotting
- **NumPy** → Fundamental numerical computations

---

## 📂 Dataset
- **Mall Customer Segmentation Data** (from Kaggle).
- A simple dataset containing 200 records with basic customer information.
- **Key Features Used**:
    - **Annual Income (k$)**: The customer's annual income in thousands of dollars.
    - **Spending Score (1-100)**: A score assigned by the mall based on customer behavior and spending nature. A higher score indicates a higher propensity to spend.

---

## 🤖 Models Implemented
- **K-Means Clustering**: An iterative, distance-based algorithm used to partition the dataset into a pre-determined number of clusters ($k$).
    - **Number of Clusters (`n_clusters`)**: Set to **5** based on the Elbow Method analysis.
    - **Initialization (`init`)**: Used `'k-means++'` for smarter initial placement of centroids, leading to faster and more reliable convergence.
    - **Random State**: Set to a fixed value to ensure reproducibility of the results.

- **DBSCAN (Bonus)**: A density-based clustering algorithm used to find clusters of arbitrary shape and identify noise points (outliers). It proved less effective for this specific dataset's structure but served as a valuable comparison.

---

## 📈 Model Evaluation & Insights
- The K-Means model successfully segmented customers into **five distinct and interpretable groups**:
    1.  **Target**: High income, high spending score.
    2.  **Careful**: Low income, low spending score.
    3.  **Standard**: Average income, average spending score.
    4.  **Sensible**: High income, low spending score.
    5.  **Careless**: Low income, high spending score.
- **Feature scaling** was confirmed to be a critical step for improving the performance and accuracy of the K-Means algorithm.
- The analysis of cluster averages provided deeper business insights, revealing, for example, the average age associated with each spending profile.
- DBSCAN identified a few outliers but struggled to form the same well-defined, convex clusters as K-Means, highlighting that the choice of algorithm should match the data's underlying structure.

---

## 📷 Visualizations
- **Initial Data Scatter Plot**: A 2D plot of Annual Income vs. Spending Score to visualize the raw data.
- **Elbow Method Curve**: A line plot showing WCSS vs. the number of clusters to determine the optimal $k$.
- **K-Means Cluster Plot**: A colored scatter plot displaying the five final customer segments with their centroids marked.
- **DBSCAN Cluster Plot**: A comparative plot showing the results of the density-based clustering approach.
