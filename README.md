# Toy-Project
First repository on GitHub

1. Create a GitHub repository.
https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/create-a-repo
2. Download the _Large Movie Review Dataset_
https://ai.stanford.edu/~amaas/data/sentiment/
The dataset has 25K reviews for training and 25K reviews for test.
3. Compute and store the TF-IDF vectors for the training set.
https://en.wikipedia.org/wiki/Tf%E2%80%93idf
There are two statistics involved: TF & IDF.
  - TF is local to the document
  - IDF is computed across all documents
Each review will be represented using a vector of tf-idf scores (one for each word in the vocabulary).
Goals at this step:
  - Store the IDF scores for all words. (to be used at inference time)
  - Compute vectorized representations for all reviews in the training set.
4. Provide predictions using KNN for the test set.
https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm
Compute the tf-idf vectors for the test set (using precomputed IDF scores). We will assume that we don't have access to all test quieries at once, therefore you'll use the IDF scores computed on the training data.
Once you have tf-idf vectors for the test set, find the K closest vectors from the training set and use the dominant class among those K to make predictions for new (test) data.
5. Make this a Kedro project.
https://kedro.readthedocs.io/en/stable/
Make your repo a Kedro project, defining two pipelines:
 - one to compute the TF-IDF vectors, and the IDF scores from the training data.
 - one to make predictions for data in the test set.
