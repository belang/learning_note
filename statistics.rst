##########
Statistics
##########

Source
======

https://www.statisticshowto.com/

Regularization
==============

Regularization is a way to avoid Overfitting_ by penalizing high-valued regression coefficients.

source
------

* https://www.statisticshowto.com/regularization/#:~:text=L1%20regularization%20adds%20an%20L1%20penalty%20equal%20to,coefficients%29%3B%20Some%20coefficients%20can%20become%20zero%20and%20eliminated.

Overfitting
===========

Overfitting is where your model is too complex for your data — it happens when your sample size is too small.
If you put enough predictor variables in your regression model, you will nearly always get a model that looks significant.

While an overfitted model may fit the idiosyncrasies of your data extremely well,
it won’t fit additional test samples or the overall population.
The model’s p-values, R-Squared and regression coefficients can all be misleading.
Basically, you’re asking too much from a small set of data.

Penalty Function Methods
========================

source: http://web.engr.oregonstate.edu/~paasch/classes/me517/week7/penalty.html

Penalty Terms
=============

Regularization works by biasing data towards particular values (such as small values near zero). The bias is achieved by adding a tuning parameter to encourage those values:

* L1 regularization adds an L1 penalty equal to the absolute value of the magnitude of coefficients.
  In other words, it limits the size of the coefficients.
  L1 can yield sparse models (i.e. models with few coefficients);
  Some coefficients can become zero and eliminated. LASSO_ regression uses this method.
* L2 regularization adds an L2 penalty equal to the square of the magnitude of coefficients.
  L2 will not yield sparse models and all coefficients are shrunk by the same factor (none are eliminated).
  Ridge regression and SVMs use this method.
* Elastic nets combine L1 & L2 methods, but do add a hyperparameter (see this paper by Zou and Hastie).

LASSO
=====

Least Absolute Shringkage and Selection Operator

The author Statist[#Statist]_ explained his idea and the development of LASSO regression in 2011.

algorithm
---------

Origin used an off-the-shelf quadratic program solver.
LARS[#LARS]_ gives an efficient way of solving the lasso.
It is a type of co-ordinate descent algorithms, which are extremely simple and fast.

The glmnet R language package implements the co-ordinate descent method for many popular models.

Features
--------

sparsity

Reference
---------

.. [#Statist] Regression shrinkage and selection via the lasso: a retrospective, J. R. Statist. Soc. B (2011) 73, Part 3, pp. 273–282
.. [#LARS] Efron et al., 2002
