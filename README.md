# Interesting-Maths-Problems

This file includes all the interesting Maths problems provided by my friends, professors or online resources. I will update this file as soon as I received new problems that is worth discussing.
## Probability 
### Question 1 Drawing until First Success in the Hypergeometric Setting 
A box contains $N$ balls, of which $r$ are red and $N-r$ are black. Balls are drawn from the box until a red ball is drawn. Show that the expected number of draws is $$\frac{N+1}{r+1}.$$
_Hint_: You may use that ```math
\sum_{x=0}^r \begin{pmatrix}N-r+x\\N-r\end{pmatrix} = \begin{pmatrix}N+1\\N-r+1\end{pmatrix}
``` Recall also that $E[X] = \sum_{x\in\mathbb{N}}P[X>x]$

### Solution
Let $X$ be the random variable denoting the number of draws needed to obtain a red ball. We want to find $E[X]$, the expected value of $X$.

Let $p$ be the probability of drawing a red ball on any given draw. On the first draw, the probability of drawing a red ball is $r/N$. If a red ball is not drawn on the first draw, then there are now $r-1$ red balls and $N-1$ balls remaining, so the probability of drawing a red ball on the second draw is $(r-1)/(N-1)$. Continuing in this way, we see that the probability of drawing a red ball on the $k$th draw is $(r-k+1)/(N-k+1)$.

Therefore, we can write the expected value of $X$ as:

$$\begin{align*}
E[X] &= 1 \cdot \frac{r}{N} + 2 \cdot \frac{r-1}{N-1} + 3 \cdot \frac{r-2}{N-2} + \cdots + k \cdot \frac{r-k+1}{N-k+1} + \cdots \
&= \sum_{k=1}^r k \cdot \frac{r-k+1}{N-k+1}
\end{align*}$$

To simplify this expression, we can use the fact that:

$$k(r-k+1) = kr - k^2 + k = kr - (k^2 - k) = kr - (k-1)k$$

Plugging this into the expression for $E[X]$, we get:

$$\begin{align*}
E[X] &= \sum_{k=1}^r k \cdot \frac{r-k+1}{N-k+1} \
&= \sum_{k=1}^r \frac{k(r-k+1)}{N-k+1} \
&= \sum_{k=1}^r \frac{kr - (k-1)k}{N-k+1} \
&= \sum_{k=1}^r \frac{kr}{N-k+1} - \sum_{k=1}^r \frac{k(k-1)}{N-k+1}
\end{align*}$$

For the first sum, we can use a partial fraction decomposition:
