# AI/ML Internship - Task 8: Clustering with K-Means - Mall Customer Segmentation

## Objective
The objective of this task was to perform unsupervised learning using the K-Means clustering algorithm to segment customers based on their annual income and spending score. This task covered essential steps from data loading and preparation to cluster evaluation.

## Dataset
The dataset used for this task is the [Mall_Customers.csv](Mall_Customers.csv) dataset, which contains information about mall customers, including `CustomerID`, `Gender`, `Age`, `Annual Income (k$)`, and `Spending Score (1-100)`.

## Tools and Libraries Used
* **Python**
* **Pandas:** For data loading and manipulation.
* **Scikit-learn:** For machine learning model implementation (KMeans, StandardScaler, silhouette_score).
* **Matplotlib:** For creating static visualizations (Elbow Method plot, cluster visualization).
* **NumPy:** For numerical operations.
* **Seaborn:** For enhanced statistical graphics.

## K-Means Clustering Steps Performed:

### 1. Load and visualize dataset
* Loaded the `Mall_Customers.csv` dataset.
* Inspected the data to understand its structure and columns.
* Selected relevant numerical features for clustering: `Annual Income (k$)` and `Spending Score (1-100)`. `CustomerID` and `Gender` were excluded.
* **Scaled** the selected features using `StandardScaler`, which is crucial for distance-based algorithms like K-Means to ensure all features contribute equally.
* Generated an initial scatter plot of the scaled `Annual Income` vs `Spending Score` to visually inspect potential clusters.
* **Outcome:** The dataset was successfully loaded, preprocessed, scaled, and an initial visual representation of the features was created, hinting at multiple natural groupings.

### 2. Fit K-Means and assign cluster labels
* Initialized the K-Means algorithm with an arbitrary number of clusters, `K=5`, for an initial fit.
* Fitted the K-Means model to the scaled data.
* Assigned cluster labels to each data point, indicating which cluster each customer belongs to.
* **Outcome:** The K-Means model successfully ran, and customers were assigned to one of five initial clusters, showing a distribution of data points across these groups.

### 3. Use the Elbow Method to find optimal K
* Implemented the Elbow Method by calculating the Within-Cluster Sum of Squares (WCSS) for a range of `K` values (from 1 to 10).
* Plotted the WCSS against the number of clusters (`K`).
* **Outcome:** The Elbow Method plot clearly showed an "elbow" at `K=5`, indicating that 5 is the optimal number of clusters for this dataset, as the reduction in WCSS significantly diminishes beyond this point.

### 4. Visualize clusters with color-coding
* Re-fitted the K-Means model using the optimal `K=5` determined from the Elbow Method.
* Obtained the final cluster labels and the coordinates of the cluster centroids.
* Generated a scatter plot of the scaled `Annual Income` vs `Spending Score`, color-coding each data point based on its assigned cluster.
* The cluster centroids were also plotted as red 'X' marks.
* **Outcome:** The visualization distinctly displayed five well-separated customer segments, with centroids accurately representing the center of each group, confirming the effectiveness of K-Means in identifying natural groupings.

### 5. Evaluate clustering using Silhouette Score
* Calculated the average Silhouette Score for the K-Means clustering with the optimal `K=5`.
* **Outcome:** An average Silhouette Score of approximately `0.5547` was obtained. This score indicates a good clustering quality, suggesting that data points are generally well-matched to their own clusters and adequately separated from other clusters.

## Visualizations
The repository includes the following generated plots:
* `customer_data_scatter.png`: Initial scatter plot of `Annual Income` vs `Spending Score`.
* `kmeans_elbow_method.png`: Plot from the Elbow Method to determine optimal K.
* `kmeans_clusters_visualization.png`: Visualization of the final K-Means clusters with color-coding and centroids.

## Conclusion
This task successfully demonstrated the end-to-end process of unsupervised learning using K-Means clustering. We effectively segmented mall customers based on their spending habits and income, determined the optimal number of clusters using the Elbow Method, and validated the clustering quality with the Silhouette Score. This approach provides valuable insights for customer segmentation and targeted marketing strategies.
