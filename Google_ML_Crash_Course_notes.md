Some thoughts from Google's Machine Learning Crash Course.

https://developers.google.com/machine-learning/crash-course/

From this:
https://developers.google.com/machine-learning/crash-course/regularization-for-simplicity/playground-exercise-examining-l2-regularization

Sometimes, overfitting happens slowly. That's why early stopping does work.


From:
https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc

Interpretation of AUC of ROC is the probability: P(f(positive sample) > f(negative sample))
i.e. the probability of the model assigning a higher score to a randomly selected positive   observation than a randomly selected negative observation.

AUC is scale-invariant. It measures how well predictions are ranked, rather than their absolute values.
AUC is classification-threshold-invariant.

Check for Prediction Bias, which is average of predictions - average of labels in data set. Never thought about it this way. You can also bucket data points and check bias for each bucket.

Sparcity:
L0 optimization is non-convex and NP-hard. Think the knapsack problem. Think of L2 vs L1 this way. Derivative of L2 penalty is 2*beta, which reduces a percentage of beta at each step. Derivative of L1 penalty is constant, which reduces a constant of beta at each step. This causes the sparsity of L1.

I still like the corners of the level curves argument better.

This is an excellent exercise:
https://developers.google.com/machine-learning/crash-course/introduction-to-neural-networks/playground-exercises

Some thoughts:
A simple network is very sensitive to initialization. What is very interesting is that slightly increasing the complexity makes it less sensitive. That's a little counter-intuitive.

This exercise shows how easy it is for a optimization to get stuck at a local optimum/saddle point.

And part three shows that feature engineering goes a long way. It is makes a model easier to train and more interpretable than using a huge network.

What is also interesting is the following. Say some configuration gives you a nice model and now you make it a little more complex. In theory, the function space is strictly larger and you should get results as least as good as the simpler model, but when running these trials, it often is not the case. A slightly more complex network structure sometimes doesn't let you replicate the performance of the simpler model.