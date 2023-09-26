# Unsupervised Learning Models for Wholesale Data 

## Brief Description

The "Wholesale Data" dataset contains a list of clients of a wholesale distributor, as well as the sum of their annual spending within various product categories.

We hope to identify patterns in cross-category purchase behaviors which allow us to differentiate, or cluster, the various 'types' of clients we might have.

We implement and optimize hyperparameters for three models: KMeans Clustering, Hierarchical Clustering, and Primary Component Analysis.

## Initial Insights
There's a strong positive correlation between purchasers of grocery products and detergents/paper products (0.92). 

These two groups are also moderately strongly correlated with purchasers of Milk (0.73 for grocery, 0.66 for detergents/paper).

## Analysis

Based on the analyzed features, our clustering models both found optimized silhouette scores using two clusters. 

Our KMeans model identified one cluster defined primarily by their purchases of Fresh Products, also finding that they were comparatively more likely to purchase frozen foods.

Our PCA suggests the optimum number of components is one, and an assessment of the model's coefficients suggest a similar interpretation to our KMeans model.

Though there is legitimate insight to be drawn from each of these results regarding cross-category purchasing behavior, I suspect all of these models suffer from insufficient outlier elimination. 

Clustering models, in particular, are highly sensitive to outliers. Our Hierarchical model was often inclined to cluster clients by total spend without significantly weighing category.

During data cleaning, we identified and investigated the nature of these outliers. We decided to leave them in our analysis for the following reasons:

1. They aren't outlandish values – that is, it isn't unthinkable that an individual client would spend that amount

2. They aren't clustered in any specific column, which may have indicated a department specific error (e.g. a corrupted file in sales reporting from the grocery department) or an anomolous event (e.g. increased sales of canned goods due to a severe storm season).

3. They aren't clustered in any specific row, which may have indicated that customer behaviors are consistent but some simply have more purchasing power than others (e.g. a grocery chain vs a convenience store).


## Challenges
Project instructions and evaluation rubric are excessively long and include a myriad of inaccurate, irrelevant, or otherwise confusing suggestions (the dataset doesn't contain information about products sold by a grocery store; the bootcamp doesn't teach R; PCA is recommended as a possible step in preparing data for PCA).
