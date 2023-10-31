# College Clustering

Applying the K-means clustering algorithm, as well as principal component analysis (PCA) dimensionality reduction, to a dataset of colleges and assessing the validity of the results.

## Dataset

The data set in this project is a csv containing data on 777 colleges with 18 features per record.

## K-means and PCA Dimensionality Reduction

The goal of this project is to see how well the k-means clustering algorithm can group colleges in the data set.  Initially, the grouping algorithm is applied on the unscaled data.  Then, the data is scaled using StandardScaler and the grouping process is repeated.  Finally, PCA dimensionality reduction is used to reduce the data to 3 features.

## Assessing Results

It is standard practice to first scale numerical data before performing a k-means grouping algorithm, however for this dataset we see that the elbow curves for both graphs fail to really "level out" as nicely as we would hope.  Already, this seems to indicate that the algorithm is having trouble assigning groups to the records in the dataset.

![unscaled-elbow](https://github.com/SamLind11/college-clustering/assets/131621692/e8ee6b37-8f6c-4505-b966-7d6d8e981c83)

![scaled-elbow](https://github.com/SamLind11/college-clustering/assets/131621692/e5ed36eb-01fa-413d-a489-c4bf8853c646)

While generating the elbow plot for the scaled data, I calculated the **silhouette score** for each value of k.  The silhouette score quantifies how separated the clusters are from one another.  The highest value occurs at k=2, with a score of 0.2396, and for k=4, the number used in the proceeding analysis, the score is 0.1783.  These are relatively low on the [-1, 1] scale for the score, which indicates that the clusters are close to overlapping and are not sufficiently distinct.

One method for achieving better groupings is to reduce the number of features using PCA dimensionality reduction.  Here, the data is reduced to just 3 features.  The **explained variance ratio** explains how much of the variance in the data set is captured by each principal component.  Summing these three ratios, we get a total of 0.6516, indicating that only about 65.2% of the variance in the entire data set is captured by the 3 components.  While the groupings created from these new features is much better (as we would expect), the features may insufficiently represent the data, and so the groupings may not be all that useful.

Reviewing some of the visualizations in the Jupyter file, we can see that there may be some **outliers** in the data.  Removing these could allow for better groupings. Additionally, future analysis should consider which features might be most important for grouping.  Given that this project did not set out with a specific set of criteria for groups, there is not any specific end goal to determine our **feature selection**.
