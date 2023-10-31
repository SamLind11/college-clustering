# College Clustering

Applying the K-means clustering algorithm, as well as principal component analysis (PCA) dimensionality reduction, to a dataset of colleges and assessing the validity of the results.

## Dataset

The data set in this project is a csv containing data on 777 colleges with 18 features per record.

## K-means and PCA Dimensionality Reduction

The goal of this project is to see how well the k-means clustering algorithm can group colleges in the data set.  Initially, the grouping algorithm is applied on the unscaled data.  Then, the data is scaled using StandardScaler and the grouping process is repeated.  Finally, PCA dimensionality reduction is used to reduce the data to 3 features.

## Assessing Results

It is standard practice to first scale numerical data before performing a k-means grouping algorithm, however for this dataset we see that the elbow curves for both graphs fail to really "level out" as nicely as we would hope.  Already, this seems to indicate that the algorithm is having trouble assigning groups to the records in the dataset.





