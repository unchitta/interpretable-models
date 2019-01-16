# Interpretability in Machine Learning

I am currently involved in a reading program at UCLA, and the current topic we are reading is interpretability in machine learning. This repo will contain theoritical notes and notebook files that demonstrate what it is and how we can implement it. The point of this is to study how to interpret models, but some models are easier to interpret than the others (thus giving an advantage of failure prevention) so we also study interpretable models and try to implement them as an example. Other methods used for model interpretation e.g. model-agnostic methods will be covered later on.

# Table of Content
1. [What is interpretability?](#what-is-interpretability)
2. [Interpretable models](#interpretable-models)
    1. [Sparse linear regression](#sparse-linear-regression)


## What is interpretability?
Borrowing definitions from the compresensive guide to interpretable machine learning by Christopher Molnar [https://christophm.github.io/interpretable-ml-book/], interpretability is the degree to which a human can consistently explain or interpret why a model makes certain decisions.

We may not always need interpretability e.g. in low-risk or extensively studied problems, but knowing the why can help us learn more about *why a model might fail*.

This also relates to tranparency and ethics: The EU for example mandates that automated decisions must be explainable and should respect fundamental rights. 


## Interpretable models
### 1. Sparse linear regression

[01-lasso-sparsity.ipynb](/blob/master/01-lasso-sparsity.ipynb)

Linear regression is very likely to be everyone's first formal introduction to inferential statistics or data science. We all know how to interpret a linear regression model, or we can learn very easily how to do so. This is an example of an interpretable model.

However, in practice, there can still be issues concerning interpretabily when using the linear regression method. What if your data has hundreds or thousands of features? How do you interpret the significance of each features? This is where sparse linear regression comes in. ***Sparsity*** refers a property of a machine learning algorithm which yields results such that some dimensions being *zero*. What I meant by this is some features of your data will have a coefficient of 0. So your coefficient vector is sparse.

One example of such a model is the least absolute shrinkage and selection operator, aka LASSO regression. Lasso regression can be thought of as normal linear regression + L1 regularization, meaning it penalizes models with large L1 norms of the coeffient. The reason why it has the variable selection property, or the sparsity property, is due to this L1 norm regularization. It can be somewhat intuitive, but I have given a presentation explaining this and the slides can be accessed [here](https://unchitta.github.io/box/interpretability-lasso.pdf).

<a href="https://unchitta.github.io/box/interpretability-lasso.pdf">(<img src="https://github.com/unchitta/interpretable-models/blob/master/images/lasso-slides-scrnshot.png" width="600">)</a>

