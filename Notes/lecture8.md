# 18.100P Lecture 8: Algebraic operations in Limits, Special Sequences
###### tags: `18.100P Lectures`
Last time
* Monotone sequences
* Squeeze Theorem
* Lims & orders, ie. $x_n \leq y_n$, then $\lim x_n \leq \lim y_n$.

Today
* Lims & alg ops
* Special sequences
* Lim sup / lim inf

---
## 1. Lims & alg ops
**Proposition:** suppose $\lim x_n = n, \lim y_n = y$, 
1. $\{x_n + y_n\}$ is also convergent, $$\lim (x_n + y_n) = \lim x_n + \lim y_n.$$
2. $\forall c \in \mathbb{R}$, $\{cx_n\}$ is convergent. $$\lim(cx_n) = c \lim x_n.$$
3. $\{x_n \cdot y_n\}$ is convergent and $$\lim (x_ny_n) = \lim(x_n) (\lim y_n).$$
4. If $\forall n \in \mathbb{N}$, $y_n \neq 0$ and $y \neq 0$, then $\frac{x_n}{y_n}$ is convergent. $$\lim (\frac{x_n}{y_n}) = \frac{\lim x_n}{\lim y_n}.$$

***Proof of (1).***
Let $\epsilon > 0$, Since $x_n \rightarrow x$, $\exists M_x \in \mathbb{N}$ s.t. $\forall n \geq M_x, |x_n - x| < \frac{\epsilon}{2}$. 
$y_n \rightarrow y$, $\exists M_y \in \mathbb{N}$ s.t. $\forall n \geq M_y, |y_n - y| < \frac{\epsilon}{2}$.
<u>WTS:</u> $\exists M \in \mathbb{N}$ s.t. $\forall n \geq M, |(x_n+y_n) - (x+y)| < \epsilon$.

$|(x_n+y_n) - (x+y)| = |(x_n-x)+(y_n-y)| \leq |x_n-x|+|y_n-y|$ by triangle inequality.

Suppose $n \geq \max(M_x,M_y)=M \Rightarrow |x_n-x|+|y_n-y| < \frac{\epsilon}{2} + \frac{\epsilon}{2} < \epsilon.$

***Proof of (2).***
<u>WTS:</u> $\exists M \in \mathbb{N}$ s.t. $\forall n \geq M$, $|cx_n-cx| < \epsilon$.
$|cx_n-cx| = |c(x_n - x)| = |c||x_n-x|$.
Since $x_n \rightarrow x$, $\exists M_x \in \mathbb{N}$ s.t.  $\forall n \geq M_x, |x_n - x| < \frac{\epsilon}{|c|+1}$.
Then, $|c||x_n-x| < |c| \cdot \frac{\epsilon}{|c|+1} < \epsilon$.
Choose $M = M_x$.

***Proof of (3).***
Since $y_n \rightarrow y$, $\exists B > 0$ s.t. $\forall n$, $|y_n| < B$.
<u>WTS:</u> $\exists M \in \mathbb{N}$ s.t. $\forall n \geq M$, $|x_ny_n - xy| < \epsilon$. $$|x_ny_n - xy|= |x_ny_n - xy_n +xy_n - xy| $$ $$= |y_n(x_n-x) + x(y_n-y)| \leq |y_n||x_n-x| + |x| |y_n-y|$$ $$\leq B|x_n-x| + |x||y_n -y| \, (RHS)$$
> To bound each under $\frac{\epsilon}{2}$.

Since $x_n \rightarrow x$, $\exists M_x \in \mathbb{N}$ s.t. $\forall n \geq M_x$, $|x_n - x| < \frac{\epsilon}{2B}$.
Since $y_n \rightarrow y$, $\exists M_y \in \mathbb{N}$ s.t. $\forall n \geq M_y$, $|y_n - y| < \frac{\epsilon}{2(1+|x|)}$.

$n \geq \max(M_x, M_y) := M$, (RHS) $< B \cdot \frac{\epsilon}{2B} + |x|\frac{\epsilon}{2(1+|x|)} \leq \epsilon$.

***Proof of (4)*.***
Let $\epsilon > 0$. It is enough to show $\lim \frac{1}{y_n} = \frac{1}{y}$. Because $\frac{x_n}{y_n} = x_n \cdot \frac{1}{y_n}$. Apply (3) to conclude.
Claim: $\exists b > 0$, s.t. $\forall n \in \mathbb{N}$, $|y_n| \geq b$. 
Since $y_n \rightarrow y$, $\exists M_0 \in \mathbb{N}$ s.t. $\forall n \geq M_0$, $|y_n - y |< \frac{|y|}{2}$
$|y| = |y-y_n + y_n| \leq |y-y_n| + |y_n| < \frac{|y|}{2} + |y_n|$ if $n \geq M_0$.
$\Rightarrow \frac{|y|}{2} < |y_n|$, if $n \geq M_0$.

What about when $n < M_0$? $|y_n| \geq \min(|y_1|, \dots, |y_{M_0-1}|) > 0$ if $n < M_0 -1$.
$b = \min(\frac{|y|}{2}, |y_1|, \dots, |y_{M_0-1}|) \leq |y_n|$ $\forall n$.
<u>WTS:</u> $\exists M \in \mathbb{N}$ s.t. $\forall n \geq M$, $|\frac{1}{y_n} - \frac{1}{y}| < \epsilon$. $$|\frac{1}{y_n} - \frac{1}{y}| = |\frac{y-y_n}{y_ny}| = \frac{|y-y_n|}{|y_n||y|} \leq  \frac{|y-y_n|}{b|y|} \text{by claim.}$$
$y_n \rightarrow y \Leftrightarrow \lim|y_n - y | = 0$. 
By (2), $\lim (\frac{1}{b|y|} \cdot |y_n - y|) = 0 \Rightarrow \lim |\frac{1}{y_n} - \frac{1}{y}| = 0$ by Squeeze Theorem.

---
**Remark:**
$k \in \mathbb{N}, \lim x_n = x$. By induction, $\lim (x_n)^k = x^k$. 
Suppose $p(z)$ is a polynomial. Show that $\lim p(x_n) = p(x)$.

---
**Remark:**
$\{x_n\}$ s.t. $x_n \geq 0$ is convergent iff $\{\sqrt{x_n}\}$ is convergent. Moreover, $\lim \sqrt{x_n} = \sqrt{\lim x_n}$.
* $x_n = \sqrt{x_n} \sqrt{x_n}$. If $\lim \sqrt{x_n}$ exists, by (3), $\lim (\sqrt{x_n})^2 = (\lim \sqrt{x_n})^2 = \lim x_n$

Suppose $x = \lim x_n$ exists.
<u>Case 1:</u> Suppose $x=0$. Since $x_n \rightarrow 0$. $\exists M_0 \in \mathbb{N}$ s.t. $\forall n \geq M_0$, $|x_n - 0| = x_n < \epsilon^2$.
$n \geq M_0$, $|\sqrt{x_n} - \sqrt{0}| = \sqrt{x_n} < \sqrt{\epsilon^2} = \epsilon \Rightarrow \sqrt{x_n} \rightarrow 0$
> $0 \leq a \leq b \Rightarrow \sqrt{a} \leq \sqrt{b}$

<u>Case 2:</u> Suppose $x > 0$. $|\sqrt{x_n} - \sqrt{x}| = |\frac{x_n - x}{\sqrt{x_n} + \sqrt{x}}| < |\frac{x_n - x}{\sqrt{x}}|$
> $x_n \rightarrow x \Leftrightarrow \lim |x_n-x| = 0$ 

Conclude by S.T., since $\lim |x_n-x| = 0$.  By (2), $\lim(\frac{1}{\sqrt{x}} \cdot |x_n - x|) = \frac{1}{\sqrt{x}}  \lim |x_n -x| = 0$.
And $\lim |\frac{x_n - x}{\sqrt{x}}| = 0$.

---

**Remark:** 
If $\{x_n\}$ is convergent and $\lim x_n = x$, then $\lim |x_n| = |x|$.
> Converse is false. $x_n = (-1)^n$.

*Proof.* Recall $\forall z \in \mathbb{R}$, $\sqrt{z^2} = |z|$. $$|x_n| = \sqrt{x_n^2}$$ By (3), $$\lim x_n^2 = x^2$$ By previous remark, $$\lim \sqrt{x_n^2} = \sqrt{x^2} = |x|$$

---

**Proposition:** 
1. If $c \in (0,1)$, then $\lim c = 0$.

> $c^n$ is monotone decreasing in (1). $\lim c^n = \inf \{c^n, n \in \mathbb{N}\}$. $\lim c^n = \lim c^{n+1}$.
> <u>Remark:</u> $x_n \rightarrow x$. Fix $k \in \mathbb{N}$. $y_n := x_{n+k}$. Then $\lim y_n = x$.
> $L = \lim c^n = lim c^{n+1} = \lim (c \cdot c^n) = c \lim c^n = c \Rightarrow L = 0$

2. If $c > 1$, then $\{c^n\}$ is unbounded.

## 2. Special Sequences
1. If $p >0$, $\lim n^{-p} = 0$.
> generalization of $\{\frac{1}{n}\} = 0$.
2. If $p > 0$, $\lim p^{\frac{1}{n}} = 1$
> root converges to 1
3. $\lim n^{\frac{1}{n}} = 1$.
> $n^\frac{1}{n} = e^{\frac{1}{n} log n}$