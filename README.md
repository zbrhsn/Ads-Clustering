# Ads-Clustering


Introduction
In unsupervised learning K means clustering is one of the most used machine learning algorithms to find out distinct group from a dataset. It helps in discovering hidden patterns, segmenting data, and enabling better decision-making in various fields like marketing, biology, and image processing. This tutorial aims to provide a detailed understanding of K-Means Clustering, using a cereal dataset as an example. We will explore the mathematical foundations, step-by-step implementation, and visual interpretation using Python.
K-Means clustering intends to partition n objects into k clusters in which each object belongs to the cluster with the nearest mean. This method produces exactly k different clusters of greatest possible distinction. The best number of clusters k leading to the greatest separation (distance) is not known as a priori and must be computed from the data. The objective of K-Means clustering is to minimize total intra-cluster variance, or, the squared error function:

 
Algorithm of K Means Clustering:
1.	Clusters the data into k groups where k  is predefined.
2.	Select k points at random as cluster centers.
3.	Assign objects to their closest cluster center according to the Euclidean distance function.
4.	Calculate the centroid or mean of all objects in each cluster.
5.	Repeat steps 2, 3 and 4 until the same points are assigned to each cluster in consecutive rounds

 

Data Overview and Objectives:
The dataset contains 150 rows and 4 columns, representing individuals and their engagement with different entertainment categories. The columns include:
•	name: Name of People
•	books: Indicating the individual's engagement with books.
•	tv_shows: Indicating the individual's engagement with TV shows.
•	video_games: Individual's engagement with video games.
There are no missing values in any column.The numerical columns (books, tv_shows, and video_games) are stored as float.
From the given values it is needed to find how many ads it need run for a agency or organization.

Pre Processing of Data:
In the preprocessing of data column named is removed as the data set is used for k means clustering which is unsupervised learning.
 

Step 1: Choose the Number of Clusters (K)
Selecting the optimal number of clusters (K) is crucial to ensure meaningful grouping. A common approach is the Elbow Method, which involves:
•	Running K-Means for different K values
•	Plotting inertia (sum of squared distances of data points from centroids)
•	Identifying the "elbow" point where inertia stops decreasing sharply
 
 
 
________________________________________
Step 2: Initialize Cluster Centroids
After selecting K, the algorithm initializes K centroids. The K-Means++ initialization is preferred as it speeds up convergence.
 
________________________________________
Step 3: Assign Data Points to the Nearest Centroid
Each data point is assigned to the closest centroid based on Euclidean distance:
 
The above code step 2 will cover the assign data point to the nearest centroid after assigning the data points to the nearest centroid the image will be like.
 
________________________________________
Step 4: Update Centroids

For cluster 2 analyse the results:
 
It shows  Students in Cluster 1 spend, on average:
•	0.6 hours reading books
•	5.1 hours watching tv shows
•	5 hours playing video games
Students in Cluster 2 spend, on average:
•	4.2 hours reading books
•	4.3 hours watching tv shows
•	6.3 hours playing video games
Let's name the clusters:
•	Cluster 1: Non-readers
•	Cluster 2: Entertainment enthusiasts

New centroid positions are computed by taking the mean of all points in each cluster:
 

Step 5: Repeat Until Convergence
Steps 3 and 4 repeat until centroids stabilize or the maximum iterations are reached.
 
Then repeat step 3 and 4 for cluster 3 and continue increase cluster till maximum iteration is reached.
From the step 2 k=3 and k=5 are the elbow but for k=5 there are some less categorial value in number. So, k=3 and k=4 is picked for final result
There are total 150 entry and for k=3 the clusters are named like below and quantity is also given below:
•	Cluster 0: Non-readers (50)
•	Cluster 1: Entertainment enthusiasts (48)
•	Cluster 2: Prefer video games to books (52)

For k=4 the name is and quantity is given below:
•	Cluster 0: Less entertainment, especially books (50)
•	Cluster 1: Less screens (36)
•	Cluster 2: Entertainment enthusiasts, especially video games (12)
•	Cluster 3: Typical students (52)

Conclusion: In this situation, looking at a combination of the results of both models, the recommendation could be to create:
1.	A general ad for the typical teen
2.	An ad targeted towards teens who don't read very much
3.	An ad targeted towards teens who love video games



