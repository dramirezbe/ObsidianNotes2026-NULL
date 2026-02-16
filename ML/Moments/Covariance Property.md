Covariance Property: The Computational Formula

The Covariance of $X$ and $Y$ is the "Mean of the Products minus the Product of the Means."

### Identity

$$Cov(X, Y) = E[XY] - E[X]E[Y]$$

$$Cov(X, Y) = E[XY] - \mu_x \mu_y$$

### Mathematical Derivation

We start with the definition of covariance and use the property that the expectation of a sum is the sum of the expectations.

1. **Definition of Covariance:**
    
    $$Cov(X, Y) = E[(X - \mu_x)(Y - \mu_y)]$$
    
2. **Expand the product (FOIL):**
    
    $$Cov(X, Y) = E[XY - X\mu_y - \mu_x Y + \mu_x \mu_y]$$
    
3. **Distribute the Expectation operator ($E$):**
    
    _Remember: $\mu_x$ and $\mu_y$ are constants, so they can be moved outside the expectation._
    
    $$Cov(X, Y) = E[XY] - E[X\mu_y] - E[\mu_x Y] + E[\mu_x \mu_y]$$
    
    $$Cov(X, Y) = E[XY] - \mu_y E[X] - \mu_x E[Y] + \mu_x \mu_y$$
    
4. **Substitute $E[X] = \mu_x$ and $E[Y] = \mu_y$:**
    
    $$Cov(X, Y) = E[XY] - \mu_y(\mu_x) - \mu_x(\mu_y) + \mu_x \mu_y$$
    
5. **Final Simplification:**
    
    Notice that $-\mu_x \mu_y - \mu_x \mu_y + \mu_x \mu_y$ leaves us with just one negative term:
    
    $$Cov(X, Y) = E[XY] - \mu_x \mu_y$$
    

---

### Interpretation

- **If $Cov(X, Y) > 0$:** $X$ and $Y$ tend to increase together (e.g., sensor temperature and CPU load).
    
- **If $Cov(X, Y) < 0$:** When $X$ increases, $Y$ tends to decrease.
    
- **If $Cov(X, Y) = 0$:** There is no linear relationship (they are uncorrelated).

![Image of positive and negative correlation scatter plots](https://encrypted-tbn0.gstatic.com/licensed-image?q=tbn:ANd9GcTyfRqFwjvvcjG6uBYQmx07RceyF77FjBJccK8z1AEpRXwa3mefLdZSQ1pQUHXw4y3U-OiV7q2TNEn831uDziN6sqiLx4XOQeVdFVkaoOtfOAm_Hn0)

