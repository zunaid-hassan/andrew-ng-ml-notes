# Module 2: Linear Regression Model - Study Notes

## Linear Regression Overview

**Definition**: A supervised learning method that fits a straight line to data to predict continuous numerical outputs.

**Key Characteristics**:

- Most widely used learning algorithm
- Predicts numbers (e.g., house prices, temperatures)
- Uses labeled training data with "right answers"

### Regression vs Classification

| Regression                       | Classification                  |
| -------------------------------- | ------------------------------- |
| Predicts continuous numbers      | Predicts discrete categories    |
| Infinitely many possible outputs | Small, finite set of outputs    |
| Example: Price prediction        | Example: Cat vs Dog recognition |

## Training Data Notation

**Standard notation used throughout machine learning**:

- **$x$** = Input variable/feature (e.g., house size)
- **$y$** = Output variable/target (e.g., house price)
- **$m$** = Total number of training examples
- **$(x^{(i)}, y^{(i)})$** = $i^{th}$ training example
  - Note: Superscript $(i)$ is an index, NOT exponentiation

**Example**: First training example: $(x^{(1)}, y^{(1)}) = (2104, 400)$

## The Model Function

**Standard form**:
$$f_{w,b}(x) = wx + b$$

Or simplified as: $f(x) = wx + b$

**Components**:

- **$w$** = Weight/coefficient (determines slope)
- **$b$** = Bias/y-intercept (where line crosses y-axis)
- **$\hat{y}$** = Predicted value (output of model)
- **$y$** = Actual true value (from training set)

**Alternative names**:

- Linear regression with one variable
- Univariate linear regression (uni = one, variate = variable)

## Cost Function

**Purpose**: Measures how well the model fits the training data

**Formula** (Squared Error Cost Function):
$$J(w,b) = \frac{1}{2m} \sum_{i=1}^{m} (f_{w,b}(x^{(i)}) - y^{(i)})^2$$

Or equivalently:
$$J(w,b) = \frac{1}{2m} \sum_{i=1}^{m} (\hat{y}^{(i)} - y^{(i)})^2$$

**Key points**:

- Computes average squared error across all training examples
- Division by $2m$ (instead of just $m$) simplifies later calculations
- Most commonly used cost function for regression problems

### How Cost Function Works

1. For each training example: compute error = $f(x^{(i)}) - y^{(i)}$
2. Square each error
3. Sum all squared errors
4. Divide by $2m$ to get average

**Goal**: Find values of $w$ and $b$ that minimize $J(w,b)$

## Visualizing the Cost Function

**For simplified model** ($f_w(x) = wx$, where $b=0$):

- Each value of $w$ creates a different line
- Each line has a corresponding cost $J(w)$
- Plotting $J(w)$ vs $w$ shows a parabola
- Minimum occurs where line best fits data

**For full model** ($f_{w,b}(x) = wx + b$):

- Cost function is 3D surface or contour plot
- Each point $(w, b)$ corresponds to a specific line and its cost
- Better fitting lines have lower costs (closer to center of contour plot)
- Goal: Find $(w, b)$ at the minimum of this surface

## Key Insights

- Small $J$ = Good fit to training data
- Large $J$ = Poor fit to training data
- Manual parameter selection is impractical
- Need automatic algorithm to find optimal $w$ and $b$
- **Next step**: Gradient descent algorithm (covered in next module)

## Important Terminology Summary

- **Training set**: Data used to train the model
- **Parameters**: $w$ and $b$ (adjusted during training)
- **Hypothesis/Model**: The function $f$ that makes predictions
- **Cost function**: $J(w,b)$ - measures prediction error
- **Minimize**: Find parameters that give smallest cost
