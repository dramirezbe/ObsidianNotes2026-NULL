
# 1. Marginal Probability

Base scenario, the probability of an event ocurring onn it's ownn
Symbol:
$$P(A)$$
$$\frac{\text{Favorable}}{\text{Total}}$$
# 2. Joint Probability

Two evets happeening at the same time
$$P(A,B)$$
- If events are INDEPENDENT you multiply it $P(A,B)=P(A)\times P(B)$
- If events are DEPENDENT we need next step
# 3. Conditional Probability

It's the probability of an event occurring **given that we already know another event has happened** 
$$P(A|B) = \frac{P(A,B)}{P(B)}$$
- If I know the sky is cloudy ($B$), I no longer care about sunny days. My new "total universe" is only the set of cloudy days, and I want to see how many of those also involve rain ($A$).

# 4. Bayes' Theorem

Sometimes it’s easy to measure $P(A|B)$, but what we actually need to know is the "inverse" probability: $P(B|A)$.

**The Logic:**

Since the joint probability $P(A,B)$ is commutative (meaning the order doesn't matter), we can express it in two different ways using the definition of conditional probability:

1. $P(A,B) = P(A|B)P(B)$
    
2. $P(A,B) = P(B|A)P(A)$

Because both expressions equal $P(A,B)$, we can set them equal to each other:

$$P(B|A)P(A) = P(A|B)P(B)$$

By dividing both sides by $P(A)$, we solve for **$P(B|A)$**:

$$P(B|A) = \frac{P(A|B) \cdot P(B)}{P(A)}$$

### Terminology breakdown:

- **$P(B|A)$ (Posterior):** Your updated belief after seeing evidence $A$.
    
- **$P(A|B)$ (Likelihood):** How well the evidence fits the hypothesis $B$.
    
- **$P(B)$ (Prior):** Your initial belief before seeing any evidence.
    
- **$P(A)$ (Evidence):** The total probability of the evidence occurring.

# 5. Example of boxes

Imagine we have two boxes containing shapes:

- **Box 1 ($B_1$):** 6 triangles and 4 circles.
    
- **Box 2 ($B_2$):** 2 triangles and 8 circles.
    

You pick a box at random with these probabilities: $P(B_1) = 0.6$ and $P(B_2) = 0.4$.

---

### 1. Marginal Probability: The Choice

The probability of picking a specific box without knowing anything about the shapes inside.

- **$P(B_1) = 0.6$**
    
- **$P(B_2) = 0.4$**
    

### 2. Conditional Probability: The Content

If you have already chosen a box, what is the chance of picking a Triangle ($T$)? This is based purely on the ratio inside that box.

- **$P(T|B_1) = 0.6$** (6 out of 10 are triangles)
    
- **$P(T|B_2) = 0.2$** (2 out of 10 are triangles)
    

### 3. Joint Probability: The Intersection

What is the probability that you choose Box 1 **and** pick a Triangle?

- **$P(T, B_1) = P(T|B_1) \cdot P(B_1)$**
    
- **$P(T, B_1) = 0.6 \cdot 0.6 = 0.36$**
    
- (Similarly for Box 2: $P(T, B_2) = 0.2 \cdot 0.4 = 0.08$)
    

### 4. Bayes' Theorem: The "Inversion"

**The Scenario:** You close your eyes, pick a box, and pull out a **Triangle**. What is the probability that it came from **Box 1**?

We need $P(B_1|T)$. We use the formula we just fixed:

$$P(B_1|T) = \frac{P(T|B_1) \cdot P(B_1)}{P(T)}$$

**Step A: Find the total Evidence $P(T)$**

To get the total probability of picking a triangle, we sum all the ways it can happen (Joint Probabilities):

$$P(T) = P(T, B_1) + P(T, B_2)$$

$$P(T) = 0.36 + 0.08 = 0.44$$

**Step B: Apply Bayes**

$$P(B_1|T) = \frac{0.36}{0.44} \approx 0.818$$

**Conclusion:** Even though you had a 60% chance of picking Box 1 originally, knowing you pulled a triangle (which is much more common in Box 1) increases your confidence to **81.8%** that you are holding Box 1.