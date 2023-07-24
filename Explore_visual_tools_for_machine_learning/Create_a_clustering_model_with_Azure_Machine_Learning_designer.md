# Create a clustering model with Azure Machine Learning designer

## Identify clustering machine learning scenarios

- *Clustering* is a form of ML that is used to group similar items into clusters based on their features
- Example of *unsupervised* ML where model is trained to separate items into clusters purely on the characteristics or *features*
- Real-world examples include:
    - Clustering customer attribute data into segments for market analysis
    - Clustering geographic coordinates into regions of high traffic in a city for a ride-share application
    - Clustering written feedback into topics to prioritize customer service changes

## Understand steps for clustering

- Similar to training for regression models ([see notes](./Create_a_regression_model_with_Azure_Machine_Learning_designer.md#understand-steps-for-regression)) however labels are not required as clustering is an *unsupervised* ML approach
- Begin with a dataset that includes multiple observations of the items you want to cluster, including numeric features that can be used to determine similarities between individual cases that will help separate them into clusters

### 2. Train model

- Apply a clustering algorithm to the dat using only the features that you have selected for clustering
- Train model on a subset of data and use the remaining subset to test the trained model
    - **K-Means Clustering** algorithm groups items into the number of clusters, or centroids, you specify (referred to as ***K***)
- K-Means algorithm works by:
    1. Initializing *K* coordinates as randomly selected points called *centroids* in *n*-dimensional space (where *n* is the number of dimensions in the feature vectors)
    2. Plotting the feature vectors as points in the same space and assigning each point to its closes centroid
    3. Moving the centroids to the middle of the points allocated to it based on the *mean* distance
    4. Reassigning the points to their closest centroid after the move
    5. Repeating steps 3 and 4 until the cluster allocations stabilize or the specified number of iterations has completed
- Use the Azure ML designer's **Assign Data to Clusters** component to group the data into clusters
    - Once all components are connected, run an experiment to use the data asset on the canvas to train a model

### 3. Evaluate performance

- When experiment run completes, metrics to evaluate performance include:
    - **Average Distance to Other Center**: indicates how close, on average, each point in the cluster is to the centroids of all other clusters
    - **Average Distance to Cluster Center**: indicates how close, on average, each point in the cluster is to the centroid of the cluster
    - **Number of Points**: number of points assigned to the cluster
    - **Maximal Distance to Cluster Center**: maximum of distances between ech point and the centroid of that point's cluster
        - Higher numbers indicate widely dispersed clusters and in combination with **Average Distance to Cluster Center** can help determine a cluster's *spread*