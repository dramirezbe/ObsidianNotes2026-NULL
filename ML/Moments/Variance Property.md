The variance can be expressed as the "Mean of the Squares minus the Square of the Mean." This is mathematically more efficient for computation because it only requires one pass through your data.

### Identity

$$Var(X) = E[X^2] - (E[X])^2$$

$$Var(X) = E[X^2] - \mu^2$$

### Mathematical Derivation

We use the **Linearity of Expectation**, where $E[aX + b] = aE[X] + b$.

1. **Definition of Variance:**
    
    $$Var(X) = E[(X - \mu)^2]$$
    
2. **Expand the binomial:**
    
    $$Var(X) = E[X^2 - 2X\mu + \mu^2]$$
    
3. **Distribute the Expectation operator ($E$):**
    
    _Note: $\mu$ and $\mu^2$ are constants, so $E[\mu] = \mu$._
    
    $$Var(X) = E[X^2] - 2\mu E[X] + E[\mu^2]$$
    
4. **Substitute $E[X] = \mu$:**
    
    $$Var(X) = E[X^2] - 2\mu(\mu) + \mu^2$$
    
5. **Final Simplification:**
    
    $$Var(X) = E[X^2] - 2\mu^2 + \mu^2$$
    
    $$Var(X) = E[X^2] - \mu^2$$
    

---

### Why use this for Sensors/Python?

If you are processing real-time sensor data (like from an ESP32 or SDR), the **Definition** formula is slow because you need to know the mean of the _entire_ dataset before you can start calculating the variance.

With the **Computational Formula**, you can track two running sums as data arrives:

1. **Sum of values:** $\sum x$ (to get $E[X]$)
    
2. **Sum of squares:** $\sum x^2$ (to get $E[X^2]$)
    

> [!TIP]
> 
> This allows you to calculate variance "on the fly" without storing thousands of previous data points in memory.