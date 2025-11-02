As of now, these aren't in any particular order. Just filling in the gaps.

# Partial Regression Plots

[Refer to this resource](https://www.youtube.com/watch?v=-eLEpMZKNDc)

# Studentized Residuals

[Resource](https://online.stat.psu.edu/stat462/node/247/)

When trying to identify outliers, one problem that can arise is when there is a potential outlier that influences the regression model to such and extent that the estimated regression function is "pulled" towards the potential outlier, so that it isn't flagged as an outlier using the standardized residual criterion. To address this issue, studentized residuals offer an alternative criterion for identifying outliers. **The basic idea is to delete the observations one at a time, each time refitting the regression model on the remaining n-1 observations. Then, we compare the observed response values to their fitted values based on the models with the ith observation deleted**. This produces **deleted residuals**. Standardizing the deleted residuals produces studentized residuals.

# Influence Plots

# Confidence Intervals

# Kurtosis

# CCPR Plots

# Leverage-Resid2 Plot

# Influence Plots

# Robust Regression to Correct for Outliers
