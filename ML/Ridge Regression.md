### Note 1: Parameter Estimation via OLS

When we move from a single mean $\mu$ to a linear model, we assume $y_i = \mathbf{x}_i^T \mathbf{w} + \epsilon_i$. To find the most likely weights $\mathbf{w}$ under Gaussian noise, we minimize the **Cost Function** $J(\mathbf{w})$.

#### 1. The Matrix Form

From the Log-Likelihood derivation, maximizing the probability is equivalent to minimizing the Sum of Squared Errors (SSE):

$$J(\mathbf{w}) = \sum_{i=1}^{N} (y_i - \mathbf{x}_i^T \mathbf{w})^2 = \|\mathbf{y} - \mathbf{X}\mathbf{w}\|^2$$

#### 2. The Derivative (Gradient)

To find the minimum, we take the derivative with respect to the weight vector $\mathbf{w}$ and set it to zero:

$$\frac{\partial J}{\partial \mathbf{w}} = -2\mathbf{X}^T(\mathbf{y} - \mathbf{X}\mathbf{w}) = 0$$

#### 3. The Normal Equations

Solving for $\mathbf{w}$ gives the closed-form solution for Ordinary Least Squares (OLS):

$$\mathbf{X}^T\mathbf{X}\mathbf{w} = \mathbf{X}^T\mathbf{y}$$

$$\mathbf{w}_{OLS} = (\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{y}$$

---

### Note 2: Ridge Regression (L2 Regularization)

In many engineering applications, the matrix $\mathbf{X}^T\mathbf{X}$ is "ill-conditioned" or singular (not invertible), often due to highly correlated features or a small $N$. **Ridge Regression** solves this by adding a penalty term.

#### 1. The Augmented Cost Function

We add the $L_2$ norm of the weights, scaled by a hyperparameter $\lambda$:

$$J(\mathbf{w})_{Ridge} = \underbrace{\|\mathbf{y} - \mathbf{X}\mathbf{w}\|^2}_{\text{MSE}} + \underbrace{\lambda \|\mathbf{w}\|^2}_{\text{Penalty}}$$

- **Small $\lambda$:** Approaches OLS (low bias, high variance).
    
- **Large $\lambda$:** Forces weights toward zero (low variance, high bias).
    

#### 2. Analytical Solution

Taking the derivative of the augmented cost function:

$$\frac{\partial J_{Ridge}}{\partial \mathbf{w}} = -2\mathbf{X}^T(\mathbf{y} - \mathbf{X}\mathbf{w}) + 2\lambda\mathbf{w} = 0$$

Solving for $\mathbf{w}$:

$$(\mathbf{X}^T\mathbf{X} + \lambda\mathbf{I})\mathbf{w} = \mathbf{X}^T\mathbf{y}$$

$$\mathbf{w}_{Ridge} = (\mathbf{X}^T\mathbf{X} + \lambda\mathbf{I})^{-1}\mathbf{X}^T\mathbf{y}$$

#### 3. Why it's called "Ridge"

The term $\lambda\mathbf{I}$ adds a "ridge" of constant values to the diagonal of the covariance matrix. This ensures the matrix is always invertible, even if $\mathbf{X}^T\mathbf{X}$ is singular.

#### 4. Bayesian Perspective

While OLS is the MLE of a Gaussian noise process, **Ridge is the MAP (Maximum A Posteriori)** estimate. It assumes the weights $\mathbf{w}$ themselves follow a Gaussian distribution centered at zero:

$$P(\mathbf{w}) \sim \mathcal{N}(0, \tau^2 \mathbf{I})$$