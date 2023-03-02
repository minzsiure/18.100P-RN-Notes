# 18.100P Lecture 7: Monotone Sequences, Subsequences, Squeeze Theorem, 
###### tags: `18.100P Lectures`
Last class
* Convergence of sequences

Today
* Monotone sequences
* Subsequences
* Squeeze Theorem
* Sequences & order algebra ops.


---
[toc]

## 1. Monotone sequence and bounded property
**Defifnition:**
* A sequence is monotone increasing if $x_n \leq x_{n+1}$. 
* A sequence is monotone decreasing if $x_n \geq x_{n+1}$.

**Examples**
* $\{\frac{1}{n}\}$ monotone decreasing to $0$. $\frac{1}{n} \geq \frac{1}{n+1}$
* $\{\frac{-1}{n}\}$ monotone increasing to $0$.  $\frac{-1}{n+1} \geq \frac{-1}{n}$

**Proposition**
* Let $\{x_n\}$ be a **monotone increasing sequence**. 
    * Then $\{x_n\}$ is convergent $\Leftrightarrow$ $\{x_n\}$ is bounded. 
* Moreover, $\lim_{x \rightarrow \infty} x_n = \sup \{x_n : n \in \mathbb{N}\}$ (converge to supremum).
> Generally, bounded does not imply convergent, i.e. $\{(-1)^n\}$
* *Proof.* 
    * $(\rightarrow)$convergent implies bounded (already shown last lecture).
    * $(\leftarrow)$ bounded implies convergent.
        * Since $\{x_n\}$ is bounded, $x:= sup \{x_n : n \in \mathbb{N}\}$ exists in $\mathbb{R}$.
        * <u>WTS:</u> $x_n \rightarrow x$.
        * Recall the definition. Let $\epsilon > 0$ be given. <u>WTS:</u> there exists some natural number $M$ s.t. $\forall n \geq M$, $|x_n - x| < \epsilon$
        * By minimality of $\sup$, $\exists M_0 \in \mathbb{N}$ s.t. $x - \epsilon < x_{M_0} \leq x < x + \epsilon$.
        * Suppose $n \geq M_0$, $x_{M_0} \leq x_n$$\Rightarrow$ $x-\epsilon < x_{M_0} \leq x_n \leq x < x + \epsilon$ by monotone increasing assumption. More clearly, $x-\epsilon < x_n < x+\epsilon \Rightarrow |x_n-x| < \epsilon$.
        * Suggested $M := M_0$.

***Corollary.***
* Let $\{x_n\}$ be monotone decreasing. Then $\{x_n\}$ is convergent $\Leftrightarrow$ $\{x_n\}$ is bounded. Moreover, $\lim_{n \rightarrow \infty} x_n = \inf \{x_n:n \in \mathbb{N}\}$.
    * $y_n := -x_n$ monotone increasing.
    * Can show $y_n \rightarrow \sup \{y_n : n\in \mathbb{N}\} = y = \sup \{-x_n : n\in \mathbb{N}\} = \inf \{x_n : n\in \mathbb{N}\}$

## 2. Subsequences
**Definition**
* Let $\{x_n\}_{n=1}^{\infty}$ be a sequnce and let $\{n_k\}_{k=1}^{\infty}$ be a strictly increasing sequence of natrual numbers.(i.e. $n_{k+1} > n_k$). The sequence $\{x_{n_k}\}_{k=1}^{\infty}$ is called a subsequence of $\{x_n\}$.
* *Remark.* Recall $\{x_n\}$, $x. \mathbb{N} \rightarrow \mathbb{R}$. $x(n) =: x_n$.
    * For a subsequence, we have a function $\mathbb{N} \rightarrow \mathbb{N}, n_k := n(k).$ $x_{n_k} = x(n(k))$.

**Example 1 (subsequences)**
* Let $\{x_n\}$ be $x_n = n$. 1, 2, 3, 4, ...
    * Odds: 1, 3, 5, ... $x_{2k-1}$
    * Evens: 2, 4, 6, ... $x_{2k}$
    * Primes: 2, 3, 5, 7, 11, ...
* Is 1, 1, ... a subsequence of $\{x_n\}$?
    * No, since it is not under an increasing set of indices.
* 1, 1, 3, 3, 5, 5, ... is also not a subsequence.

**Example 2 (subsequences)**
* $x_n := (-1)^n$
    * Then 1, 1, 1, ... is a subsequnce of $\{x_n\}$, aka $\{x_{2k}\}_{k=1}^{\infty}$.
    * -1, -1, -1, ... is subsequence $\{x_{2k-1}\}_{k=1}^{\infty}$.
    > An example of a divergent sequence having convergent subsequences.

**Proposition.**
* If $\{x_n\}$ is convergent, then any subsequences $\{x_{n_k}\}$ is also convergent to x. (*subsequencial limit is the same*)
* *Proof.*
    * Suppose $lim_{n \rightarrow \infty}\{x_n\} = n$. Let $\epsilon > 0$, there exists $M_0 \in \mathbb{N}$ s.t. $\forall n \geq M_0$, $|x_n - x| < \epsilon$ (*).
    * <u>WTS:</u> there exists $M \in \mathbb{N}$, s.t. for all $k \geq M$, $|x_{n_k} - x| < \epsilon$.
        * *Claim.* Any natrual number $k$, $n_k \geq k$ by strictly increasing property. (Consequence of $n_k$ strictly increasing).
        * Choose $M = M_0$. If $k \geq M_0 \Rightarrow n_k \geq k \geq M_0$.
        * Apply (*) with $n = n_k \Rightarrow |x_{n_k} - x| < \epsilon$.

## 3. Squeeze Theorem (sandwich)
Let $\{a_n\}$, $\{b_n\}$, $\{x_n\}$ be sequences s.t. $\forall n \in \mathbb{N}$, $a_n \leq x_n \leq b_n$. 
* Suppose $a_n \rightarrow x$, $b_n \rightarrow x$. $\Rightarrow x_n \rightarrow x$.
* Useful to find lower and upperbound that converges to something to show the convergence of the middle sequence.

*Proof.*
> Sketch: use convergence of $a_n$, $b_n$, then use assumption of squeeze.
* <u>WTS:</u> Given $\epsilon > 0$, $\exists M \in \mathbb{N}$ s.t. $\forall n \geq M$, $|x_n - x| < \epsilon$.
* Since $a_n \rightarrow x$, $\exists M_a \in \mathbb{N}$ s.t. $\forall n \geq M_a$, $|a_n - x| < \epsilon$ $\Rightarrow x-\epsilon < a_n$.
* Since $b_n \rightarrow x$, $\exists M_b \in \mathbb{N}$ s.t. $\forall n \geq M_b$, $|b_n - x| < \epsilon$ $\Rightarrow b_n < x+\epsilon$.
* Introduce, $M := \max\{M_a, M_b\}$, if $n \geq M$, $\Rightarrow x-\epsilon < a_n, b_n < x+\epsilon$.
* $a_n \leq x_n \leq b_n \Rightarrow x-\epsilon < a_n \leq x_n  \leq b_n < b_n + \epsilon \Rightarrow x-\epsilon < x_n < x + \epsilon \Leftrightarrow |x_n - x| < \epsilon$.

**Corollary: $x_n \rightarrow x \Leftrightarrow |x_n - x| \rightarrow 0$**

**Example**
$x_n = \frac{n^2}{n^2+2n+1}$
* Claim: $x_n \rightarrow 1$.
* *Proof.* Enough to show by Corollary $|x_n - 1| = |\frac{n^2}{n^2+n+1} - 1| \rightarrow 0$
    * $|\frac{n^2}{n^2+n+1} - 1| = |\frac{n^2 - (n^2+n+1)}{n^2+n+1}|$ $= |\frac{n + 1}{n^2+n+1}|$
    * Find $a_n \leq |\frac{n + 1}{n^2+n+1}| \leq b_n$ s.t. $a_n \rightarrow 0, b_n \rightarrow 0$.
        * Choose $a_n = 0$.
        * Choose $b_n = \frac{n+1}{n^2+n} = \frac{1}{n}$.
    * Conclude by S.T.


## 4. How do limits behave w.r.t. order?
*Propositions (order preserves under limit).*
1. Let $\{x_n\}$ and $\{y_n\}$ be convergent and $\forall n \in \mathbb{N}$, $x_n \leq y_n$. Then $\lim_{n\rightarrow \infty}x_n \leq \lim_{n \rightarrow \infty} y_n$.
2.  If $\{x_n\}$ is convergent and $\forall n \in \mathbb{N}$, $a\leq x_n \leq b$, then $a\leq \lim_{n\rightarrow \infty}x_n \leq b$.
* *Proof for (1).*
    * Let $x := \lim x_n$, $y := \lim y_n$.
    * <u>WTS:</u> $x \leq y$. 
    * Suppose $x > y$ for the sake of contradiction. 
    * > Need a smart choice of $\epsilon$.
    * Since $y_n \rightarrow y$, $\exists M_y \in \mathbb{N}$ s.t. $\forall n \geq M_y$, $|y_n - y| < \frac{x-y}{2} =: \epsilon$
    * Since $x_n \rightarrow y$, $\exists M_x \in \mathbb{N}$ s.t. $\forall n \geq M_x$, $|x_n - x| < \frac{x-y}{2} =: \epsilon$
    * Take $M = M_x + M_y \geq \max(M_x, M_y)$.
    * Apply with $n = M$, $|y_M - y| < \frac{x-y}{2} \Rightarrow y_M < y + \frac{x-y}{2} = \frac{x+y}{2} < \frac{-(x-y)}{2} + x$.
    * $|x_M - x| < \frac{x-y}{2} \Rightarrow x < x_M + \frac{x-y}{2} \Leftrightarrow x - \frac{x-y}{2} < x_M$.
