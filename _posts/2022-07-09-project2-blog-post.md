Project 2
================

I need to add two links: username.github.io/repo-name site and the repo
itself

[GitHub Pages Repo](https://brknapp.github.io/Project_1/) <br> [Regular
Repo](https://github.com/chsueh2/ST558-Project2)

For Project 2, I practiced summarizing data with an exploratory data
analysis (EDA), creating linear regression and ensemble tree-based
models, and automating Markdown reports.

# What Would I Do Differently?

At first, I struggled to do the EDA because I did not know where to
start or which variables to focus on. I began by making graphs that just
focused on one or two variables. I realized that I would need to do this
analysis for all of the variables (including the numeric and
categorical). At first, my EDA did not flow very well because it did not
tell a story about the entire data set. My partner helped me set up a
plan for my EDA, which helped it flow better (e.g., start with graphing
the response variable and then graph the rest of the variables). I then
learned how to make multiple graphs (one for each variable) at the same
time so that we could compare them. If I was able to do this part again,
I would start by planning out my EDA and deciding which variables to
visualize first. Then, I would prepare tables/graphs to explain each
variable.

# What was the Most Difficult Part?

The most difficult part of this project was understanding how to
automate this process. I remember learning how to do this in RMarkdown
in lecture by setting parameters and using the `apply` and `render`
functions. I was not sure how to apply this to GitHub. My partner showed
me how to do this with a function.

# What are the Big Take-Aways from this Project?

Every model has its upsides and downsides. For example, a tree model is
more flexible than a simple linear regression model (SLR) because a tree
model splits up the predictor space into regions and then averages all
the values within each region to make a prediction whereas an SLR fits
one line for the entire data set. This gives a tree model more
flexibility than an SLR, but it may increase the variance.

One way to decrease the variance of trees is to use the average
prediction from many trees as our final prediction (e.g., random forest
and boosted tree models). If the predictions are independent from one
another, taking the average is a great way to reduce variation. But, if
the data set has a strong predictor, then all the trees will probably
use that predictor for their first split, resulting in trees that are
highly correlated with one another. To fix this, we can use a random
forest model because it uses a random subset of predictors in each tree
instead of including every predictor in each tree. However, there is a
risk of overfitting. One way to fix this is to use a boosted tree model,
which trains each tree sequentially so that every tree that’s created is
based off the previous one. However, boosted tree models are affected by
outliers.

You need to pick the best model based off of the data and the resulting
statistics, like the standard deviation of the prediction errors, or
root mean square error.
