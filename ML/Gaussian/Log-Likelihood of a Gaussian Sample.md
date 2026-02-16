	
	When we have a collection of $N$ independent and identically distributed (**i.i.d.**) samples $\{X_1, X_2, \dots, X_N\}$, the joint probability (Likelihood) is the product of their individual PDFs.
	
	### 1. The Product Form
	
	$$P(X \mid \mu, \sigma^2) = \prod_{i=1}^{N} \mathcal{N}(X_i \mid \mu, \sigma^2)$$
	
	Substituting the Gaussian PDF:
	
	$$P(X \mid \mu, \sigma^2) = \prod_{i=1}^{N} \left[ \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left( -\frac{(X_i - \mu)^2}{2\sigma^2} \right) \right]$$
	
	### 2. Applying the Logarithm
	
	Applying $\ln$ turns the product ($\prod$) into a summation ($\sum$):
	
	$$\ln P(X \mid \mu, \sigma^2) = \sum_{i=1}^{N} \ln \left[ \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left( -\frac{(X_i - \mu)^2}{2\sigma^2} \right) \right]$$
	
	### 3. Expanding the Logarithm
	
	Using log rules ($\ln(ab) = \ln a + \ln b$):
	
	$$\ln P(X \mid \mu, \sigma^2) = \sum_{i=1}^{N} \left[ \ln \left( \frac{1}{\sqrt{2\pi\sigma^2}} \right) + \ln \left( \exp\left( -\frac{(X_i - \mu)^2}{2\sigma^2} \right) \right) \right]$$
	
	Expanding the first term ($\ln(1/A) = -\ln A$) and simplifying the exponent:
	
	$$\ln P(X \mid \mu, \sigma^2) = \sum_{i=1}^{N} \left[ -\frac{1}{2} \ln(2\pi\sigma^2) - \frac{(X_i - \mu)^2}{2\sigma^2} \right]$$
	
	### 4. Final Distributed Form
	
	Since the first term $-\frac{1}{2}\ln(2\pi\sigma^2)$ does not depend on $i$, we can pull it out of the sum by multiplying by $N$:
	
	$$\ln P(X \mid \mu, \sigma^2) = -\frac{N}{2} \ln(2\pi\sigma^2) - \frac{1}{2\sigma^2} \sum_{i=1}^{N} (X_i - \mu)^2$$
	
	---
	
	### Why this is the "Magic" of Statistics
	
	This expansion reveals two critical components used in your Python data processing:
	
	1. **The Constant Term:** $-\frac{N}{2} \ln(2\pi\sigma^2)$ acts as a baseline.
	    
	2. **The Sum of Squared Errors (SSE):** $\sum (X_i - \mu)^2$.
	    
	
	To maximize the probability (Maximum Likelihood Estimation), you want the log-likelihood to be as close to zero as possible (since probabilities are $\leq 1$, logs are negative). This is achieved by **minimizing the Sum of Squared Errors**.
	
> 	[!IMPORTANT]
> 	
> 	This is exactly why "Least Squares" works. Minimizing the distance between your model and your data is mathematically equivalent to maximizing the likelihood of a Gaussian noise process.