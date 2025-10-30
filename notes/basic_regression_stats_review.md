# Measuring the Quality of Fit

In the regression setting, the most commonly-used measure is the **mean squared error (MSE)**, given by

![Alt image](../images/mse_formula.png)

where `f_hat(xi)`1 is the prediction that `f_hat` gives for the *i*th observation. The MSE above is computed using the training data and should more accurately be referred to as the **training MSE**. We don't care much about how well the method works on the training data. Rather, **we are interested in the accuracy of the predictions that we obtain when we apply our method to previously unseen test data**. 

# The Bias-Variance Trade-Off

The U-shape observed in the test MSE (shown below) turns out to be the result of the bias-variance trade-off.

![Alt image](../images/mse_u_curve.png)

It's possible to show (but we're not going to) that the expected test MSE, for a given value x0, can always be decomposed into the sum of three fundamental quantities: the **variance, the squared bias, and the variance of error terms**.

This effectively tells us that in order to minimize the expected test error, we need to select a statistical learning method that simultaneously achieves **low variance and low bias**. Note that variance and squared bias are inherently a nonnegative quantities. 

**Variance** refers to the amount by which f hat would chance if we estimated it using a different training data set. Ideally, the estimate for f should not vary too much between training sets. However, if a method has a high variance, then small changes in the training data can result in large changes in f hat. In general, **more flexible statistical methods have higher variance**.

Consider the following:

![Alt image](../images/model_flexibility_graph.png)

The flexible green curve is following the observations very closely. It has high variance because changing one of these data points may cause the estimate to change considerably. In contrast, the least squares line is relatively inflexible and has low variance, because moving any single observation will likely cause only a small shift in the position of the line.

On the other hand, **bias** refers to the error that's introduced by approximating a real-life problem, which may be extremely complicated, by a much simpler model. For example, linear regression assumes that there is a linear relationship. It's unlikely that any real-life problem truly has such a simple linear relationship, and so performing linear regression will undoubtedly result in some bias in the estimate of f.

As a general rule, as we use more flexible methods, the variance will increase and the bias will decrease. Don't forget that **flexibility refers to a model's "curvy-ness" when graphing the model equation**. This comes with the assumption that the model is an adequate representation of the training data.

However, **at some point increasing flexibility has little impact on the bias but starts to significantly increase the variance**. When this happens the test MSE increases.

# Linear Regression Statistical Measurements

## Residual Sum of Squares (RSS)

You're already very familiar with this. It's simply the sum of the difference of all residuals resulting from the model. Let's move on.

## Standard Error (SE)

Following an analogy of the estimation of the population mean µ of a random variable Y. A natural question is as follows: how accurate is the sample mean µ hat as an estimate of µ? The average of µ hats over many data sets will be very close to µ, but a single estimate of µ hate may be a substantial under or overestimate of µ. How far off will that single estimate of µ hat be? In general, we answer this question by computing the **standard error of µ hat**. We have the formula

![Alt image](../images/se_formula.png)

Roughly speaking, the **standard error tells us the average amount that the estimate µ hat differs from the actual value of µ. The above equation tells us that this deviation shrinks with *n* - the more observations we have, the smaller the SE of µ hat**. We can use similar methods for estimating beta hat 0 and 1.

## Residual Standard Error (RSE)

Same thing as SE, just concerning the residuals. For the RSE formulas to be strictly valid, **we need to assume that the errors for each observation have common variance (SD^2) and are uncorrelated**. This estimate of SD is given by the formula

![Alt image](../images/rse_formula.png)

**Standard errors are used to compute confidence intervals**. A 95% confidence interval is defined as a range of values such that with 95% probability, the range will contain the true unknown value of the parameter. The range is defined in terms of lower and upper limits computed from the sample of data.

A 95% confidence interval has the following property: if we take repeated samples and construct the confidence interval for each sample, 95% of the intervals will contain the true unknown value of the parameter.

**Standard errors can also be used to perform hypothesis tests on the coefficients**. The most common hypothesis test involves testing the **null hypothesis of

H0: There is no relationship between X and Y

versus the alternative hypothesis

Ha: There is some relationship between X and Y.

Mathematically, this corresponds to testing

![Alt image](../images/hypothesis_test.png)

## t-statistic

