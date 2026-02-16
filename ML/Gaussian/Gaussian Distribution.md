## The Gaussian Distribution (Normal Distribution)

A continuous random variable $X$ follows a Gaussian distribution if its PDF is defined by the mean ($\mu$) and the variance ($\sigma^2$).

### 1. Probability Density Function (PDF)

$$p(x) = \mathcal{N}(x \mid \mu, \sigma^2) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x - \mu)^2}{2\sigma^2}}$$

- **Pre-factor $\frac{1}{\sqrt{2\pi\sigma^2}}$**: This is the normalization constant that ensures the total area under the curve is exactly 1.
    
- **Exponent**: The term $(x - \mu)^2$ creates the symmetric "bell" shape centered at $\mu$.
    

---

### 2. Derivation of the Expected Value $E[X]$

To prove that $E[X] = \mu$ for a Gaussian, we solve the integral:

$$E[X] = \int_{-\infty}^{\infty} x \cdot \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x - \mu)^2}{2\sigma^2}} dx$$

#### Step 1: Change of Variables

Let $z = x - \mu$, which means $x = z + \mu$ and $dx = dz$.

As $x \to \pm\infty$, $z \to \pm\infty$.

$$E[X] = \int_{-\infty}^{\infty} (z + \mu) \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{z^2}{2\sigma^2}} dz$$

#### Step 2: Split the Integral

Break the integral into two separate parts:

$$E[X] = \underbrace{\int_{-\infty}^{\infty} z \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{z^2}{2\sigma^2}} dz}_{\text{Part A}} + \underbrace{\int_{-\infty}^{\infty} \mu \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{z^2}{2\sigma^2}} dz}_{\text{Part B}}$$

#### Step 3: Solve Part A (The Odd Function)

The function $f(z) = z e^{-z^2}$ is an **odd function** ($f(-z) = -f(z)$).

The integral of an odd function over symmetric limits $(-\infty, \infty)$ is always **zero**.

$$\text{Part A} = 0$$

#### Step 4: Solve Part B (The Total Probability)

Pull the constant $\mu$ out of the integral:

$$\text{Part B} = \mu \int_{-\infty}^{\infty} \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{z^2}{2\sigma^2}} dz$$

The integral remaining is the definition of a PDF summed over its entire range, which by definition equals **1**.

$$\text{Part B} = \mu \cdot 1 = \mu$$

### Final Result

$$E[X] = 0 + \mu = \mu$$
