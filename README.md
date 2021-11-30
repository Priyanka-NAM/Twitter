# Twitter - Buzz in Social Media Dataset

## Motivation

In the age of social media, any information, either good or bad, can be a buzz. In this project, we evaluate different classification methods to determine whether a social media post (Twitter posts in particular) is a buzz. Finding buzz posts can be helpful in finding misinformation and stopping its spread.  It can also be used to determine the success or failure of a newly released product or service. The first step in either of these use cases would be to identify a social media buzz post which can be accomplished using the classification methods discussed below.

## Objective

The main purpose of this project is to examine a subset of the UCI Dataset for Social Media Buzz i.e., Twitter and to develop a model ensemble that can accurately characterize a social media data point as a buzz or not. 

## Dataset Details

The dataset includes 77 features and over 500,000 data points.
Each instance is defined by 77 features, which describe the evolution of 77 primary features through time. 
Each of these attributes contains 7 time instances.
There are no missing values in the data.

![image](https://user-images.githubusercontent.com/67281829/144115453-91d379dc-82ff-4155-997a-eb3831d888d3.png)

## Voting Classifier Results

| Classifier | Parameters | Accuracy |
|---|---|---|
| Logistic Regression | solver='newton-cg',max_iter (Maximum Iterations) = 300, C (Regularization) = 100 | 0.965889 |
| K Nearest Neighbors Classifier | N(Neighbors) = 30 | 0.961910 |
| Linear SVC | C (Regularization) = 10, max_iter (Maximum Iterations) = 20000 | 0.9661739 |
| Decision Tree Classifier | max_depth (Maximum Depth) = 3 | 0.963899 |
| Voting Classifier (Hard Voting) | estimators=['Logistic Classifier', 'KNN Classifier', 'Decision Tree Classifier', 'Linear SVC Classifier'] | 0.9653212 |
| Voting Classifier (Soft Voting) | estimators=['Logistic Classifier', 'KNN Classifier', 'Decision Tree Classifier'] | 0.965605 |

## Analysis of results

Linear SVC performed better compared to hard and soft voting classifiers. Linear SVC does not produce any probability vector and thus could not be used with the soft voting algorithm. Even though hard voting used four classifiers and soft voting used only three, the soft voting ensemble seems to be performing better only next to Linear SVC. 

## Conclusion

We hit the maximum accuracy of .97 with SoftVoting Ensemble method with Logistic regression, K nearest neighbor and Decision Tree as base learning algorithm.

Out of top 5 classifiers, three algorithms were of ensemble type either boosting or Voting classifier. It shows that ensemble is a good classifier contender to consider along with individual algorithms. The ensemble methods can be utilised to extract better understanding and relationships in the data. However, It is not always possible to stitch algorithms together, ensembling algorithms can easily result in loss in accuracy as compared to individual algorithms if base learning algorithms are selected blindly.

Finally, we can say that algorithms with accuracy with .97 or more shows a great promise and confidence in classifying a tweet into the right category, and  can be used to make better decisions and recommendations as suggested in the motivation section.

We can see and compare all the estimators used in the process and make better judgements on the right model selections.

![image](https://user-images.githubusercontent.com/67281829/144116394-9fc69b4b-1f45-42bd-961e-217e35ae69b9.png)

![image](https://user-images.githubusercontent.com/67281829/144116473-e5bd7773-0dae-4321-b008-332cacf9824f.png)

