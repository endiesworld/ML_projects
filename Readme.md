# ML Pipeline

![Machine Learning Pipeline](#) ![./imges/ML_pipeline.png](https://github.com/endiesworld/ML_projects/blob/main/images/ML_pipeline.png)

## Supervised Learning

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

### Collinear Variables

Oftentimes, many variables move together in systematic ways. Such a problem is called **collinearity** for two variables. We also call the two variables correlated variables. If there are more than two variables that are correlated, it is called **multicollinearity**. How can we detect multicollinearity?
A **correlation matrix** is the best way to investigate multicollinearity. A correlation matrix is an ensemble of the correlations of all variables.
Figure 2 is the correlation matrix for the dependent variable and independent variables in our model. The correlation of different variables is shown on the upper right triangle of the correlation matrix. The diagonal of the correlation matrix is the correlation for the variable itself, which is always 1. The lower left triangle of the correlation matrix actually provides the same correlation information as the upper right triangle.

![Correlation Matrix](#) ![./imges/correlation_matrix.png](https://github.com/endiesworld/ML_projects/blob/main/images/correlation_matrix.png)

#### Dependent Variable and Independent Variables

As seen in the matrix, let's examine our dependent variable. KO's excess return is fairly positively correlated with three independent variables: Dow 30 Index excess return, Pepsi excess return, and Google excess return. Therefore, we can see that these three variables are pretty good at explaining KO's excess return variation.

#### Low-Correlated Independent Variables

Now let's turn our focus just on independent variables. First, we'll first look at KO's revenue growth, Walmart excess return and Starbucks' excess return. They are the 3 variables that have low correlation with other independent variables. However, they also have low correlation with our dependent variable: KO excess return.

#### High-Correlated Independent Variables

In the matrix, the Dow 30 Index excess return has a high correlation with Google's excess return and Bank of America's excess return. Google's excess return also has a high correlation with Pepsi's excess return. With these four fairly correlated independent variables in our model, will they present any issues to our regression result?

#### Impact of Multicollinearity in Regression Model

If independent variables are highly correlated, the variances, standard errors and covariances of the coefficients from the regression model may be large. Then, the estimates of the coefficient will be less precise because the confidence intervals for the coefficient estimates will be wide.
The high standard errors for the coefficient estimates also mean the estimates are less likely to be statistically significant. The
R^2 and adjusted R^2 may be high because the whole model is still good. The collinearity issue makes it hard to separate the individual impact from correlated independent variables in the model.
Even though it is hard to isolate each variable's impact in the model, the model can still be a good choice to forecast if the new data from the independent variables have the same collinear issue as the sample data used to build the model.

### Methods to Address Multicollinearity

#### Method 1

This first method to reduce the impact of multicollinearity is to drop independent variables that have high correlation. Usually, the correlation between 0.8 and 0.9 is considered high correlation. You can drop one of the correlated variables from the model and run it again to see if the model improves. The problem with using this method is that it only considers the relationship between two variables one at a time. This method doesn't address multicollinearity with more than two variables. Sometimes, using correlation alone cannot find this issue.

#### Method 2

The second method is to treat one of the independent variables in the model as a dependent variable and run a regression with the rest of the independent variables. We can use this method to determine if any of the independent variables can be explained by the other independent variables.

## Discriminative, Predictive, and Generative AI

### Discriminative Models

Machine Learning (ML) has progressed significantly with the advent of Deep Learning and Transformer Architecture, providing two prime categories:

1. Discriminative (Predictive) AI
2. Generative AI

Discriminative AI excels in categorization, and spotting boundaries in data to predict outcomes. Examples of discriminative models include:

- Decision Trees
- Linear Regression
- Convolutional Neural Networks (CNNs)
- Recurrent Neural Networks (RNNs)

### Generative AI

Generative AI shines in creating new data resembling the input, with models like:

- Generative Adversarial Networks
- Variational Autoencoders

The choice between these paths is based on:

- Task complexity
- Data quality
- Computational resources.

## Model Accuracy and Loss

### Model Accuracy

This is the fraction of predictions our model got right. Accuracy tells you how often the model's predictions match the actual labels. It’s an evaluation metric rather than a training signal.

### Model Loss measures

Measres how far the model's predictions are from the actual class labels. It is a measure of the model's error.
Loss quantifies how wrong the model's predictions are. It’s the output of the loss function (like MSE or cross-entropy) that the optimizer uses to update weights.

- Used During Training to adjust weights via backpropagation

- Numerical Value: Can be any positive real number — lower is better.

🧠 Think of loss as a student's raw exam score. It doesn't directly tell you how well they ranked, just how far off they are from perfect.
For a Classification model, the typical Loss Function is Cross-Entropy Loss (categorical or binary), while for Regression Model, the typical Loss Function is Mean Squared Error (MSE)
**Binary Cross-Entropy:** - is commonly used in binary classification tasks. It calculates the loss for each instance by comparing the predicted probability with the actual label (either 0 or 1), and then takes the average over all instances.
**Interpretation:** - lower loss values are better, indicating that the model's predictions are closer to the actual labels. A high loss value means the model's predictions are far off from the actual labels.
