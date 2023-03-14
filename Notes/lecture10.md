# 18.100P Lecture 10
Last time
* limsup, liminf
* Cauchy Sequences

Today
* Cauchy Sequences
* Series

---

# 1. Cauchy
> should know basic manipulation of Cauchy for the midterm.

**Definition:**  $\{x_n\}$ is Cauchy if $\forall \epsilon > 0, \exists M \in \mathbb{N}$ s.t. $\forall n, k \geq M$, $|x_n - x_k| < \epsilon$.

---
**Proposition 1.** $\{x_n\}$ is Cauchy $\Rightarrow$ bounded.
***Proof.*** Since $\{x_n\}$ is Cauchy, $\exists M \in \mathbb{N}$ s.t. $\forall n,k \geq M$, $|x_n - x_k| < 1$.
Let $n \geq M$, $|x_n| = |x_n-x_M+x_M| \leq |x_n - x_M| + x_M < 1 + |x_M|$.
> Take care of finitely many elements:

$n \leq M-1$, $|x_n| \leq \max(|x_1|, \dots, |x_{M-1}|)$.
$\Rightarrow \forall n \in \mathbb{N}$, $|x_n| \leq \max(|x_1|, \dots, |x_{M-1}|, 1 + |x+M|).$ $\square$

---
**Proposition 2.** Suppose $\{x_n\}$ is Cauchy, and suppose there is a subsequence $\{x_{n_k}\}$ s.t. $x_{n_k} \rightarrow x \in \mathbb{R}$. Then $x_n \rightarrow x$.
> If you want to show a Cauchy sequence converges, it is enough to show one of its subsequences converges, and the sequence converges to what the subsequence converges to.

***Proof.*** Let $\epsilon > 0$ be given. 
1. By definition, $x_{n_k} \rightarrow x \Rightarrow \exists M_0 \in \mathbb{N}$ s.t. $\forall k \geq M_0$, $|x_{n_k} - x| < \frac{\epsilon}{2}$. 
2. Since $\{x_n\}$ is Cauchy, $\exists M_1 \in \mathbb{N}$ s.t. $\forall n, l \geq M_1$, $|x_n - x_l| < \frac{\epsilon}{2}.$ 

Introduce $M = \max(M_0, M_1)$. Suppose $n \geq M$, $|x_n - x| = |(x_n - x_{n_m}) + (x_{n_m} - x)| \leq |x_n - x_{n_m}| + |x_{n_m} - x|$ by triangle inequality.
Since $n \geq M \geq M_1$, and recall for subsequence indices $n_k$, we always have $n_k \geq k$, then $n_M \geq M \geq M_1$. And, $M \geq M_0$ By (2), $|x_n - x_{n_m}| + |x_{n_m} - x| \leq \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon. \square$

---

**Corollary.** $\{x_n\}$ is Cauchy iff $\{x_n\}$ is convergent.
> Cauchy implies convergence for real numbers only.
> Show Cauchy is easier than show convergence.

***Proof.*** 
$(\rightarrow)$ If $\{x_n\}$ is Cauchy, then by Proposition 1, $\{x_n\}$ is bounded. By Bolzano-Weierstrass Theorem, there is a subsequence $\{x_{n_k}\}$ such that $x_{n_k} \rightarrow x \in \mathbb{R}$. By Proposition 2, $x_{n_k} \rightarrow x$.

$(\leftarrow)$  Suppose $\{x_n\} \rightarrow x$, then by the definition of convergence, given $\epsilon > 0$, $\exists M \in \mathbb{N}$ s.t. $\forall n \geq M$, $|x_n - x| < \frac{\epsilon}{2}$. 
> common trick: add and subtract same number. We use $x$ in this case.

Suppose $n, k \geq M$, $|x_n - x_k| = |(x_n - x) + (x - x_k)| \leq |x_n - x| + |x - x_k| < \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon.$ Thus $\{x_n\}$ is Cauchy. $\square$

## 2. Series
> Motivates the foundation of the analysis. 
> The convergence of series is given meaning by looking at the convergence of partial sum.

**Definition:** Given a sequence $\{x_n\}$, the symbol $\sum_{n=1}^{\infty} x_n$ or $\sum x_n$ is the <u>series</u> associated to  $\{x_n\}$. We say that $\sum x_n$ <u>converges</u> if the sequence $s_m = \sum_{n=1}^{m} x_n$ (called $m^{th}$ partiaul sum) converges. Moreover, if $\lim_{m \rightarrow \infty} s_m = s$, then we write $s = \sum x_n$.

<u>Remark:</u> A series need not start at $n=1$, i.e. $\sum_{n=100}^{\infty} x_n = \lim_{m \rightarrow \infty} \sum_{n=100}^{m} x_n$.

---

### A) Example 1
$x_n = \frac{1}{n(n+1)}$. We claim $\sum_{n=1}^{\infty}  \frac{1}{n(n+1)}$ converges to $1$.

Let $m \in \mathbb{N}$, $s_m = \sum_{n=1}^{m} \frac{1}{n(n+1)} = \sum_{n=1}^{m} \frac{1}{n} -\frac{1}{n+1} = \sum_{n=1}^{m} \frac{1}{n} - \sum_{n=1}^{m} \frac{1}{n+1} = \sum_{n=1}^{m} \frac{1}{n} - \sum_{n=2}^{m+1} \frac{1}{n} =1-\frac{1}{m+1}.$
$\lim_{m \rightarrow \infty} s_m = \lim_{m \rightarrow \infty} (1 - \frac{1}{m+1}) = \lim_{m \rightarrow \infty} 1 -  \lim_{m \rightarrow \infty} \frac{1}{m+1} = 1 - 0 = 1$.

### B) *Example 2: geometric series
*Claim.* If $|r| < 1$, then $\sum_{n=0}^{\infty} r^n$ converges and $\sum_{n=0}^{\infty} r^n = \frac{1}{1-r}$.

*Proof.* Let $m \in \mathbb{N}$, $s_m = \sum_{n=0}^{m} r^n = \frac{1-r^{m+1}}{1-r}$ by induction.
$lim_{m \rightarrow \infty} s_m = lim_{m \rightarrow \infty}(\frac{1-r^{m+1}}{1-r}) = \frac{lim_{m \rightarrow \infty} 1-r^{m+1}}{lim_{m \rightarrow \infty} 1-r} = \frac{lim_{m \rightarrow \infty} 1- lim_{m \rightarrow \infty} r^{m+1}}{1-r} = \frac{1-0}{1-r} = \frac{1}{1-r}. \square$
> Recall if $|c| < 1$, then $\lim_{n \rightarrow \infty}|c|^n \rightarrow 0$

---
<u>Observation:</u> 
> We are interested in the asymptotic behavior!

Let $\{x_n\}$ be a sequence, and let $M \in \mathbb{N}$, $\sum_{n=1}^{\infty} x_n$ converges iff $\sum_{n=M}^{\infty} x_n$ converges. 
Let $m \geq M$. It follows from $\sum_{n=1}^{m} x_n = \sum_{n=1}^{M} x_n + \sum_{n=M}^{m} x_n$. Denote $\sum_{n=1}^{m} x_n$ to be $s_m$, denote $\sum_{n=M}^{m} x_n$ to be $\bar{s_m}$. $$\lim_{m \rightarrow \infty} s_m = \lim_{m \rightarrow \infty} \bar{s_m} + \sum_{n=1}^{M} x_n$$.

---

**Definition:** $\sum x_n$ is Cauchy if the sequence of partial sums $s_m = \sum_{n=1}^{M} x_n$ is Cauchy.
> To show something converges, it is sufficient to show it is Cauchy, which is easier.

***Proposition 1.*** $\sum x_n$ is Cauchy $\Leftrightarrow$ $\sum x_n$ is convergent.

***Proposition 2.*** $\sum x_n$ is Cauchy iff $\forall \epsilon > 0$, $\exists M \in \mathbb{N}$ s.t. $\forall l > m \geq M$, $|\sum_{n=m+1}^{l} x_n| < \epsilon$.
***Proof.***
($\Rightarrow$)
Suppose $\sum x_n$ is Cauchy. Then given $\epsilon >0$, $\exists M_0 \in \mathbb{N}$ s.t. $\forall m, l \geq M_0$, $|s_m - s_l| < \epsilon$ (*). 
Choose $M = M_0$. Suppose $l < m$, $$|\sum_{n=m+1}^{l} x_n| = |s_l - s_m| < \epsilon \text{ by (*)}$$

($\Leftarrow$) left as an exercise.

---

### C) Divergence Test
If $\sum x_n$ converges, then $\lim_{n \rightarrow \infty} x_n = 0$.
> contrapositive is the divergence test.

**Proof.** Suppose $\sum x_n$ converges $\Rightarrow$ $\sum x_n$ is Cauchy $\Rightarrow$ given $\epsilon > 0$, $\exists M_0 \in \mathbb{N}$ s.t. $\forall l > m \geq M_0$, $|\sum_{n=m+1}^{l} x_n| < \epsilon$. $|x_{m+1}| = |\sum_{n=m+1}^{m+1}x_n| < \epsilon$ by (*) with $l = m+1$, assuming $m \geq M_0$. Choose $M = M_0 + 1$. We have shown for any $k \geq M$, $|x_k| < \epsilon$. $\square$  

<u>Remark:</u> if $|r| < 1$, the divergence test implies $\sum r^n$ diverges.