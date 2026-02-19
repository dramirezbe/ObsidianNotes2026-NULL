
**Source:** [Linear combinations, span, and basis vectors | Chapter 2, Essence of linear algebra](http://www.youtube.com/watch?v=k7RM-ot2NWY)

## 1. Vector Coordinates as Scalars
* A vector like $\begin{bmatrix} 3 \\ -2 \end{bmatrix}$ uses its coordinates as **scalars** [00:00:35].
* These scalars stretch or squish the fundamental vectors of the coordinate system.

## 2. Basis Vectors ($\hat{i}$ and $\hat{j}$)
* **$\hat{i}$ (i-hat):** The unit vector pointing to the right, representing the x-direction [00:00:50].
* **$\hat{j}$ (j-hat):** The unit vector pointing straight up, representing the y-direction [00:00:56].
* Any standard 2D vector is the sum of these scaled basis vectors:
  $$\begin{bmatrix} 3 \\ -2 \end{bmatrix} = 3\hat{i} + (-2)\hat{j}$$
* *Alternative Basis:* You can choose any two non-aligned vectors as a new basis to create an entirely valid, alternative coordinate system [00:01:51].

## 3. Linear Combinations
* **Definition:** The process of scaling vectors and adding them together [00:03:04].
* **Formula:** For vectors $\vec{v}$ and $\vec{w}$ and scalars $a$ and $b$, a linear combination is written as:
  $$a\vec{v} + b\vec{w}$$
* *Why "linear"?* If you fix one scalar and let the other vary freely, the tip of the resulting vector draws a straight line [00:03:12].

## 4. The Span
* **Definition:** The set of all possible vectors that you can reach with a linear combination of a given set of vectors [00:04:06].
* **Visualizing Span in 2D:**
  * **All of 2D Space ($\mathbb{R}^2$):** The span of most pairs of 2D vectors covers the entire infinite flat plane.
  * **A Single Line:** If the two vectors line up (are collinear), their span is restricted to a single line passing through the origin [00:04:26].
  * **The Origin:** If both are zero vectors, the span is just the origin.
* *Visualization Tip:* When dealing with infinite sets of vectors, conceptualize each vector simply as a single point where its tip sits, rather than drawing arrows [00:04:46].

## 5. Span in 3D Space
* Taking two non-collinear vectors in 3D space yields a span that forms a flat 2D sheet (a plane) cutting through the origin [00:06:04].
* Adding a third vector introduces a third scalar:
  $$a\vec{u} + b\vec{v} + c\vec{w}$$
* **Scenario A:** If the third vector points in a completely separate direction, varying its scalar sweeps the 2D plane through all of 3D space ($\mathbb{R}^3$) [00:07:47].
* **Scenario B:** If the third vector already sits on the span (the plane) of the first two, the overall span doesn't change [00:07:29].

## 6. Linear Dependence vs. Independence
* **Linearly Dependent:** Occurs when multiple vectors are present and at least one is redundant—removing it doesn't reduce the span [00:08:20].
  * *Mathematical Translation:* One of the vectors can be expressed as a linear combination of the others (e.g., $\vec{u} = a\vec{v} + b\vec{w}$).
* **Linearly Independent:** Occurs when each vector adds a completely new dimension to the span. No vector is trapped in the span of the others [00:08:58].

## 7. The Technical Definition of a Basis
* Bringing the terminology together, the strict definition of a basis of a space is: **A set of linearly independent vectors that span that space** [00:09:10].