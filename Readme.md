# Supervised Learning

**Endogenous Variable:** An endogenous variable, also called a dependent variable, is a variable whose value is determined by the model.
**Exogenous Variable:** An exogenous variable, also called an independent variable, is a variable whose value is determined outside of the model or is given to us.

## Relashionships between Endogenous Variable and Exogenous Variables

After defining endogenous variables and exogenous variables for our regression model, we will use some graphical tools to investigate the relationships of our selected variables. This step is important because these graphs can give us information as to how to structure our regression model and decide if some selected variables and data points should be excluded.
One of the assumptions in running regression analyses is that the endogenous variable has a linear relationship with exogenous variables.
If the straight line drawn is either a horizontal line or a vertical line, it means no matter how much the value of one variable moves, the value of the other variable always stays within a tight range. In this case, the two variables are independent of each other. If an exogenous variable is independent of the endogenous variable, we should drop this exogenous variable from the model.
An outlier is a point that doesn't follow the general trend of the other points. The other one is called a leverage point. A leverage point has extreme value for exogenous variables. Both types may or may not impact the estimated result of the regression model. Try to run one model with them and another model without them. Then, compare the two model results to see if these extreme points are crucial to the final model result.

**Scatter plot:** A scatter plot is a two-dimensional graph with one variable on one axis and another variable on another axis. A scatter plot can show us the relationship of two variables.

## Use cases for Scatter plot

- linear relationship check between two variables
- independence relattionship check between two variables
- extreme points check.

## Covariance and Correlation(Finance as Case Study)

Covariance is a metric to measure the amount of movement the two variables exhibit. Here is the covariance formula:
Cov(X, Y) = E[(X - E[X]) (Y - E[Y])]

- If the covariance has a positive sign, it means the two variables move in the same direction.
- If the covariance has a negative sign, the two variables move in opposite directions.
- If the covariance is 0, the two variables are linearly uncorrelated (uncorrelated).

The higher the absolute value of the covariance of the two variables, the stronger the (positive or negative) relationship the two variables have. The downside of covariance is its value changes when the scales of two variables change. Because of this issue, we use correlation more often in data analysis.

Correlation is also a metric to measure the co-movement of the two variables. However, it eliminates the scale issue mentioned above by dividing covariance with the square root of the multiplication of the two variables' variances. Here is the correlation math formula:

            Corr(X, Y) = Cov(X, Y) / sqrt(Var(X) * Var(Y))

- Unlike covariance, the value of correlation is limited between -1 and 1.
- If the correlation of two variables is greater than 0, the two variables are positively correlated.
- If the correlation of two variables is less than 0, the two variables are negatively correlated.
- If two variables are perfectly positively correlated, the correlation will be 1.
- If two variables are perfectly negative correlated, the correlation will be -1.
- If the correlation is 0, the two variables are linearly uncorrelated.

![Correlation Demonstration Graphs](#) ![./imges/correlation_diagram.png](https://github.com/endiesworld/ML_projects/blob/main/images/correlation_diagram.png)
