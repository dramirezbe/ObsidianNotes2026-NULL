# Probability Density Function (PDF)

In continuous space, we don't look at the probability of a single point (which is 0), but rather the **density** around it.

### Comparison Table

|**Concept**|**Discrete (PMF)**|**Continuous (PDF)**|
|---|---|---|
|**Summation**|$\sum P(x) = 1$|$\int_{-\infty}^{\infty} f(x) dx = 1$|
|**Marginal**|$P(x) = \sum_y P(x, y)$|$f(x) = \int f(x, y) dy$|
|**Conditional**|$P(A \mid B) = \frac{P(A,B)}{P(B)}$|$f(x \mid y) = \frac{f(x,y)}{f(y)}$|
|**Expected Value**|$E[X] = \sum x P(x)$|$E[X] = \int x f(x) dx$|

---

### Key Properties

The probability of a variable falling within a specific interval $[a, b]$ is the area under the curve:

$$P(x \in [a,b]) = \int_{a}^{b} f(x) \, dx$$

- **Non-negativity:** $f(x) \geq 0$ for all $x$.
    
- **Total Area:** The total area under the PDF must equal 1.
    

### Expected Value & Variance

The **Expected Value ($E[X]$)** represents the long-term average or "center of mass" of the distribution.

**Discrete Expected Value (Sample Mean):**

$$\mu_x = \frac{1}{N}\sum_{n=1}^{N}X_n$$

**Continuous Expected Value:**

$$E[X] = \int_{-\infty}^{\infty} x f(x) \, dx$$

**Variance ($Var(X)$):**

Measures the "spread" of your data around the mean.

$$Var(X) = E[(X - \mu)^2] = \int (x - \mu)^2 f(x) \, dx$$

---

### Quick Explanation

- **PDF vs. PMF:** In discrete sets (like a dice roll), you have specific "buckets" of probability. In continuous signals (like sensor noise or voltage), there are infinite possible values. We use integration because we are summing up an infinite number of infinitesimal points.
    
- **Marginalization:** Think of this as "collapsing" a dimension. If you have data for $x$ and $y$ but only care about $x$, you integrate out all the $y$ values.
    
- **Conditional PDF:** This describes the behavior of $x$ given that you already know the value of $y$. It’s essentially a "slice" of a 3D distribution, normalized so the area of that slice equals 1.
    

![Image of probability density function area under curve](https://encrypted-tbn0.gstatic.com/licensed-image?q=tbn:ANd9GcR2zDX-pBdFz4Fl9viWjIhnakd7VBYfDhrglX3yBKnDLmBn-zO4QJXT7AmkEmgEgfy-53R6tWxR0-V1wiQ9NBGuHkHzNNrxY-O51CWQMw4QssohAzE)