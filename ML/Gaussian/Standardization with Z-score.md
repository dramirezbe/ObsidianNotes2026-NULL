We use $z = \frac{x - \mu}{\sigma}$ to simplify the Gaussian integral. This is called **Standardization**.

### Why use it?

1. **Simplification:** It turns the complex exponent $-\frac{(x - \mu)^2}{2\sigma^2}$ into simply $-\frac{z^2}{2}$.
    
2. **Dimensionless:** It removes the units. $z$ tells you how many "standard deviations" a point is from the mean.
    
3. **Integration:** It makes solving the Gaussian integral much cleaner.
    

---

### Derivation of $E[X]$ using $z = \frac{x - \mu}{\sigma}$

**1. Define the substitution:**

$$z = \frac{x - \mu}{\sigma} \implies x = \sigma z + \mu$$

$$dx = \sigma dz$$

**2. Plug into the Expected Value integral:**

$$E[X] = \int_{-\infty}^{\infty} (\sigma z + \mu) \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{z^2}{2}} (\sigma dz)$$

**3. Simplify the constants:**

Notice that the $\sigma$ from $dx$ cancels out with the $\sqrt{\sigma^2}$ (which is $\sigma$) in the denominator:

$$E[X] = \int_{-\infty}^{\infty} (\sigma z + \mu) \frac{1}{\sqrt{2\pi}} e^{-\frac{z^2}{2}} dz$$

**4. Split the integral:**

$$E[X] = \sigma \underbrace{\int_{-\infty}^{\infty} z \frac{1}{\sqrt{2\pi}} e^{-\frac{z^2}{2}} dz}_{\text{Part A}} + \mu \underbrace{\int_{-\infty}^{\infty} \frac{1}{\sqrt{2\pi}} e^{-\frac{z^2}{2}} dz}_{\text{Part B}}$$

**5. Evaluate:**

- **Part A:** $z$ is odd, $e^{-z^2/2}$ is even. Their product is **odd**. The integral over symmetric limits is **0**.
    
- **Part B:** This is the PDF of the **Standard Normal Distribution** $\mathcal{N}(0,1)$. The area under the curve is **1**.
    

**Result:**

$$E[X] = \sigma(0) + \mu(1) = \mu$$
