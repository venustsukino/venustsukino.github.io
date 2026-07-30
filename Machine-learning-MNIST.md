# Classifying Handwritten Digits: A Comparative Machine Learning Study

## Overview
This project compared classical machine learning methods against deep learning on the 
MNIST handwritten digit dataset (70,000 images), evaluating the trade-offs between 
predictive accuracy, computational cost, model complexity, and interpretability.

## What I did
- Trained and compared three baseline classifiers on raw pixel data: logistic regression, 
  a decision tree, and linear discriminant analysis (LDA)
- Applied Principal Component Analysis (PCA) to test whether dimensionality reduction 
  improves performance or mainly affects computational efficiency
- Built and tuned a feedforward neural network, then a convolutional neural network (CNN), 
  experimenting with regularisation (dropout), batch normalisation, and different optimisers
- Analysed misclassification patterns via confusion matrices to understand why certain 
  models struggled with visually similar digits

## Key findings
- Logistic regression achieved the best baseline accuracy (92.6%) but at a high 
  computational cost (114.5s training time)
- PCA proved to be primarily a computational optimisation rather than a performance 
  booster: reducing to 100 components preserved almost identical accuracy (92.2%) while 
  cutting training time by an order of magnitude, but this benefit didn't extend to 
  decision trees, which performed worse and slower with PCA applied
- The CNN achieved the highest accuracy (99.0%), correctly classifying ~680 more digits 
  than PCA-logistic regression, but took over 15x longer to train and offered far less 
  model interpretability
- Overall conclusion: logistic regression with PCA offers the best real-world balance 
  of accuracy, speed, and interpretability for most applications, while the CNN is best 
  reserved for high-stakes use cases (e.g. identity verification) where maximum accuracy 
  justifies the added cost

## Why it matters
This project demonstrated a practical, decision-oriented approach to model selection — 
not just building the most accurate model, but evaluating which model is actually 
fit for purpose given real-world constraints like training time, computational cost, 
and the need for explainability. That trade-off is directly relevant to security contexts, 
where models (e.g. for anomaly or intrusion detection) must be both accurate and 
auditable.
