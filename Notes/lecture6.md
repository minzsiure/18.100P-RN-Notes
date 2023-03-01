# 18.100P Lecture 6
Last class
* Ordered fields
* Sequences

Today
* Continue on Sequences

---
## 1. Sequence
Recall a sequence is 
* $X. \mathbb{N} \rightarrow \mathbb{R}$. $x(n) = x_n \in \mathbb{R}$. Or $\{x_n\}^{\infty}_{n=1}$.
* For a sequence to be **bounded**, $\exists M > 0$ s.t. $\forall n \in \mathbb{N}, |x_n| \leq M$.
* A sequence $\{x_n\}$ **converges** to $x \in \mathbb{R}$ iff $\forall \epsilon > 0, \exists M \in \mathbb{N}$ s.t. $\forall n \geq M$, $|x_n - x| < \epsilon$.
* A sequence converges to some limit is said to be <u>convergent</u>.
    * Otherwise, the sequence is <u>divergent</u>.

### A) Exercise: negation of converges
$\{x_n\}$ does not converge to $x \in \mathbb{R}$ if $\exists \epsilon > 0$, s.t. $\forall M \in \mathbb{N}$, $\exists n \in \mathbb{N}$ which satisfies $n \geq M$, s.t. $|x_n - x| \geq \epsilon$.

### B) Proposition: If $\{x_n\}$ converges to $x$ and $y$, then $x=y$.
(*Limits are unique*)
***Lemma.*** If $x,y \in \mathbb{R}$ and $\forall \epsilon > 0$, $|x-y| \leq \epsilon$, then $x=y$.
* (reverse direction that $x=y$ then $|x-y| \leq \epsilon$ is trivial)
* *Proof.* Argue by contradiction. Suppose $x \neq y \Leftrightarrow$ $|x-y|>0$. This is equivalent to saying $\exists a > 0$ s.t. $|x-y| \geq a$. Choose $\epsilon = \frac{|x-y|}{2}$. Since $|x-y| > \frac{|x-y|}{2} = \epsilon$, we reach a contradiction.

**Prove the original proposition,**
* We will show that $\forall \epsilon > 0$, $|x-y| \leq \epsilon$. Suffices by lemma
* Given $\epsilon > 0$, 
    * $x_n \rightarrow x \Rightarrow \exists M_1 \in \mathbb{N}$ s.t. $\forall n \geq M_1$, $|x_n - x| < \frac{\epsilon}{2}$.
    *  $x_n \rightarrow y \Rightarrow \exists M_2 \in \mathbb{N}$ s.t. $\forall n \geq M_2$, $|x_n - y| < \frac{\epsilon}{2}$.
    *  Let $M = max\{M_1, M_2\}$. Then $n \geq M \Rightarrow$ $n \geq M_1, n \geq M_2$.
> Important trick!
*  Choose $n \geq M$,
    *  $|x-y| = |(x_n - y) + (x-x_n)| \leq |x_n - y| + |x-x_n| < \epsilon$
    *  Reduce to lemma, $x=y$. $\square$

\* If $x_n \rightarrow x$, write $x = \lim_{n\rightarrow \infty}x_n$
## 2. Examples of Convergence

### Ex1
Define $x_n := c \in \mathbb{R}$, $\forall n \in \mathbb{N}$. Then $\lim_{n\rightarrow \infty}x_n = c$.

Given $\epsilon > 0$, $|x_n - c| = 0$ $\forall n \in \mathbb{N}$, by deifnition above. Choose $M = 1 \Rightarrow \forall n \geq M, |x_n - c| < \epsilon$.

### Ex2
Define $x_n := \frac{1}{n}$. Then $\lim_{n\rightarrow \infty}\frac{1}{n} = 0$

*Claim.* If $\epsilon > 0$, then $\exists M \in  \mathbb{N}$ s.t. $\forall n \geq M$, $\frac{1}{n} < \epsilon$.
*Proof.* 
* Archimedean property states, given $x > 0, y \in \mathbb{R}$, $\exists m \in \mathbb{N}$ s.t. $mx > y$. 
    * By AP, with $x = \epsilon, y = 1$, $\exists M^* \in \mathbb{N}$ s.t. $M^* \epsilon > 1 \Leftrightarrow \epsilon > \frac{1}{M^*}$.
    * $n\geq M^* \Rightarrow \frac{1}{n} \leq \frac{1}{M^*} < \epsilon$
* $|x_n - 0| = |x_n| = \frac{1}{n}$ by definition. Choose $M$ as above $\Rightarrow n \geq M, |x_n - 0| = \frac{1}{n} < \epsilon$.

### Ex3
$x_n := \frac{1}{n^2+2n+100}$. Then $\lim_{n\rightarrow \infty} x_n = 0$.
*Proof.*
* $|x_n - 0|$ = $\frac{1}{n^2+2n+100}$ < $\frac{1}{2n}$.
* Since  $\frac{1}{n} \rightarrow 0$, given $\epsilon > 0$, $\exists M \in \mathbb{N}$ s.t. $\forall n \geq M$, $\frac{1}{n} < \epsilon$.
* $\frac{1}{n} < \epsilon \Rightarrow \frac{1}{2n} < \frac{\epsilon}{2}$
    * $|x_n - 0|$ = $\frac{1}{n^2+2n+100}$ < $\frac{1}{2n} < \frac{\epsilon}{2} < \epsilon$.

## 3. Nonexamples of divergence
### NEx1
*Claim.* $x_n := (-1)^n$ is divergent.
* Given $x \in \mathbb{R}$, $\lim_{n\rightarrow \infty} (-1)^n \neq x \Leftrightarrow \exists \epsilon > 0$ s.t. $\forall M \in \mathbb{N}$, $\exists n \geq M$ with $|(-1)^n - x|>\epsilon$
* $|(-1)^M - (-1)^{M+1}| = 2$.
    * > trick again!
    * $|((-1)^M - x) + (x - (-1)^{M+1})| \leq |(-1)^M - x| + |x - (-1)^{M+1}|$
        * Say $M$ is odd, $x > 0$, $(-1)^M - x = -1 - x < -1 \Rightarrow |(-1)^M - x| > 1$
        * Say $M$ is even, $x - (-1)^{M+1} = x - (-1) = x + 1 > 1 \Rightarrow |x - (-1)^{M+1}| > 1$.
    * *Claim.* $|(-1)^M - x| \geq 1$ or $|x - (-1)^{M+1}| \geq 1$.
        * Choose $\epsilon = \frac{1}{2}$. Given $M \in \mathbb{N}$, choose $n = M$ or $M+1$ so $n \geq M$. $|x_n - x| \geq 1 > \epsilon$. 
        * (There are always elements in the sequence that is at least a distance 1 away from some given real number $x$, so divergence.)

## 4. Proposition: if $\{x_n\}$ is convergent, then $\{x_n\}$ is bounded.
*Proof.* If $\{x_n\} \rightarrow x$, given $\epsilon > 0$, $\exists M \in \mathbb{N}$ s.t. $n \geq M$, $|x_n - x| < \epsilon$. 
Choose $\epsilon = 1 \Rightarrow \forall n \geq M$, $|x_n - x| < 1$.
> Bounded means $\exists B > 0$ s.t. $|x_n| \leq B$  $\forall n$

Suppose $n \geq M$, $|x_n| = |x_n - x + x| \leq |x_n - x| + |x|$, so $|x_n| < 1 + |x|$.

What about $|x_n|$ when $1 \leq n < M?$
> Trick is take the max.
* Choose $B := \max \{|x_1|, \dots , |x_{M-1}|, 1 + |x|\}$
* *Claim.* $\forall n \in \mathbb{N}$, $|x_n| \leq B$.
    * $n \geq M$, $|x_n| < 1 + |x| \leq B$ by definition of max.
    * $1 \leq n < M$, $|x_n| \leq B$ by definition of max. $\square$


> **Converse is FALSE!** An example is $x_n := (-1)^n$ is bounded by 1 but does not converge.

## 5. Monotone Sequence
A sequence $\{x_n\}$ is said to be <u>monotone increasing</u> if $\forall n \in \mathbb{N}$, $x_n \leq x_{n+1}$. $\{x_n\}$ is <u>monotone decreasing</u> if $\forall n \in \mathbb{N}$, $x_n \geq x_{n+1}$.

If $\{x_n\}$ is MI or MD, we say that $\{x_n\}$ is *monotone*, or *monotonic*.

> For example $\frac{1}{n}$ is monotone decreasing to 0, $-\frac{1}{n}$ is monotone increasing to 0, $(-1)^n$ is not MI or MD.