# 18.100P Lecture 9: Limsup/Liminf, Bolzano-Weierstrass, Cauchy Sequences
Last time
* Lims & alg ops
* Special sequences

Today
* Lim sup / Lim inf
* Bolzano-Weierstrass
* Cauchy Sequences
* Midterm topics

Next class
* Cuachy implies bounded.
* Cauchy is *equivalent* to convergent (completeness of real numbers)

---
[toc]

## Does a bounded sequence have a convergent subsequence?

## 1. Limsup/Liminf
***Definition.*** Let $\{x_n\}$ be a bounded sequence, we define  (assuming they exist) $$\lim_{n \rightarrow \infty} \sup x_n := \lim_{n \rightarrow \infty} \sup\{x_k:k\geq n\}$$
$$\lim_{n \rightarrow \infty} \inf x_n := \lim_{n \rightarrow \infty} \inf\{x_k:k\geq n\}$$

> $\lim_{n \rightarrow \infty} \sup\{x_k:k\geq n\}$ and $\lim_{n \rightarrow \infty} \inf\{x_k:k\geq n\}$ 
are well defined by below proposition.

***Proposition.*** Let $\{x_n\}$ be a bounded sequence. Let $$\{a_n\} := \sup \{x_:k\geq n\},$$ $$\{b_n\} := \inf \{x_k:k \geq n\}$$
1. $\{a_n\}$ is bouned and monotone decreasing, 
and $\{b_n\}$ is bounded and monotone increasing.
2. $\lim_{n \rightarrow \infty} \inf x_n \leq \lim_{n \rightarrow \infty} \sup x_n$

***Proof.***
1. $\forall n \in \mathbb{N}$, $\{x_k : k \geq n+1\} \subset \{x_k : k\geq n\}$ 
**Monotone decreasing:**
$\Rightarrow a_{n+1} = \sup \{x_k : k \geq n+1\} \leq \sup \{x_k : k \geq n\} = a_n$
$\Rightarrow b_{n+1} = \inf \{x_k : k \geq n+1\} \geq \inf \{x_k : k \geq n\} = b$
**Bounded:**
$\{x_n\}$ is bounded $\Leftrightarrow$ $\exists B > 0$ s.t. $-B \leq x_n \leq B$
$-B \leq \inf \{x_k : k \geq n\} \leq \sup \{x_k : k \geq n\} \leq B$ by definition of sup and $B$ upperbound.
$\Rightarrow -B \leq b_n \leq a_n \leq B$ (*)
Since $\{a_n\}$ is monotone decreasing and bounded, $\lim a_n = \inf \{a_m : m \geq 1\}$. 
Since $\{b_n\}$ is monotone increasing and bounded, $\lim b_n = \sup \{b_m : m \geq 1\}$.
$b_n \leq a_n \forall n \Rightarrow \lim b_n \leq \lim a_n$.
2. Thus this implies assetion (2), $\lim \inf x_n \leq \lim \sup x_n$.

## 2. Examples
***Example (1).***
$(-1)^n = x_n$. For $n \in N$, $\{x_k : k \geq n\} = \{-1, +1\}$.
* $a_n = \sup \{x_k : k\geq n\} = \sup \{-1,1\} = 1$
* $b_n = \inf \{x_k : k\geq n\} = \inf \{-1,1\} = -1$
$\Rightarrow \lim a_n = 1, \lim b_n = -1$

***Example (2).***
$\{x_n\} = \frac{1}{n}$ Fix $n \in N$, $\{x_k : k \geq n\} = \{\frac{1}{k}:k \geq n\}$.
* $a_n = \sup \{\frac{1}{k} : k\geq n\} = \frac{1}{n}$
* $b_n = \inf \{\frac{1}{k} : k\geq n\} = 0$
$\Rightarrow \lim a_n = 0, \lim b_n = 0$
> **Remark: If $\{x_n\}$ is convergent $\lim x_n = x$, then $\lim \sup x_n = \lim \inf x_n = x$**.

## 3. Bounded sequences have convergent subsequences
***Proposition.*** 
Let $\{x_n\}$ be bouned sequence. 
Then there exists subsequences $\{x_{n_k}\}$, $\{x_{m_k}\}$ s.t.
$$\lim x_{n_k} = \lim \sup x_n,$$ 
$$\lim x_{m_k} = \lim \inf x_n.$$

***Proof.*** [come back review]
Let $a_n = \sup \{x_k : k \geq n\}$.
$\exists n_1 \in N$ s.t. $a_{1-1} \leq x_{n_1} \leq a_1$
>$a_{n_{1+1}} = \sup \{x_k:k \geq n_1+1\}$

$\exists n_2 > n_1$ s.t. $a_{n_{1+1}} - \frac{1}{2} < x_{n_2} \leq a_{n_{1+1}}$
Continue the same argument, $\exists n_3 > n_2$ s.t. $a_{n_{2+1}} - \frac{1}{3} < x_{n_3} \leq a_{n_{2+1}}$
Continuing, we obtain $n_1 < n_2 < n_3 < \dots$ s.t. $a_{n_{k+1}} - \frac{1}{k+1} < x_{n_k} \leq a_{n_{k+1}}$
Recall that $a_n = \sup \{x_k:k\geq n\}$ is convergent to $\lim \sup x_n$. 
$a_{n_{k+1}}$ is a subsequence of $a_n$, therefore $\lim_{k\rightarrow \infty} a_{n_{k+1}} = \lim_{n\rightarrow \infty} \sup x_n$
$\lim_{k\rightarrow \infty} (a_{n_{k+1}} - \frac{1}{k+1}) = \lim_{k\rightarrow \infty} a_{n_{k+1}} - \lim_{k\rightarrow \infty} \frac{1}{k+1} = \lim_{n\rightarrow \infty}x_n - 0$
By Squeeze Theorem, $\lim_{k\rightarrow \infty}x_{n_k} = \lim_{n\rightarrow \infty} x_n$.

## 4. Bolzano-Weierstrass Theorem
> An immediate result of the above proposition.

***Theorem.*** 
Every bounded sequence $\{x_n\}$ has a convergent subsequence $\{x_{n_k}\}$

***Proposition.***
Let $\{x_n\}$ be a bounded sequence. Then $\{x_n\}$ converges iff $\lim \inf x_n = \lim \sup x_n$. Moreover, if $\{x_n\}$ converges, then $\lim \inf x_n = \lim \sup x_n = \lim x_n$.

***Proof.***
$(\Leftarrow)$
Suppose $\lim \inf x_n = \lim \sup x_n$ (*). We show $\{x_n\}$ converges.
Let $n \in N$. $\inf \{x_k: k \geq n\} \leq x_n \leq \sup \{x_k: k \geq n\}.$
Let $a_n = \sup \{x_k: k \geq n\}, b_n = \inf \{x_k: k \geq n\}$. 
Recall by definition, $\lim a_n = \lim \sup x_n$,  $\lim b_n = \lim \inf x_n$. By (*), $\lim a_n = \lim b_n$.
By Squeeze Theorem, $\lim b_n = \lim x_n = \lim a_n.$

$(\Rightarrow)$
Suppose $\{x_n\}$ converges and $\lim x_n = x$. We show $\lim \inf x_n = \lim \sup x_n$.
$\{x_n\}$ converges $\Rightarrow$ any subsequence $\{x_{n_k}\}$ is also convergent to $x$. 
We saw by previous proposition that 
* There exists a subsequence $\{x_{n_k}\}$ s.t. $\lim_{k \rightarrow \infty} x_{n_k} = \lim \sup x_n \Rightarrow x = \lim \sup x_n$. 
* There exists subsequence $\{x_{m_k}\}$ s.t.$\lim_{k \rightarrow \infty} x_{m_k} = \lim \inf x_n \Rightarrow x = \lim \inf x_n$.

## 5. Cauchy Sequences
A sequence $\{x_n\}$ is <u>Cauchy</u> if $\forall \epsilon > 0, \exists M \in N$ s.t. $\forall n,k \geq M$, $|x_n - x_k| < \epsilon$.
***Example (1)***
$x_n = \frac{1}{n}$ is Cauchy.
Let $\epsilon > 0$, and choose $M > \frac{2}{\epsilon}$. If $k,n \geq M$, $|\frac{1}{n} - \frac{1}{k}| \leq |\frac{1}{n}| + |\frac{1}{k}| < \epsilon \Rightarrow k,n>\frac{2}{\epsilon} \Leftrightarrow \frac{\epsilon}{2} > \frac{1}{n}, \frac{1}{k}.$

***Non-example (1)***
$\{x_n\}$ is <u>not Cauchy</u> if $\exists \epsilon > 0$, s.t. $\forall M \in N$, $\exists n,k \geq M$, s.t. $|x_n - x_k| \geq \epsilon.$
> can be useful to show a sequence does not converge by showing it is not Cauchy.

i.e. $(-1)^n = x_n$ is not Cauchy. 
Choose $\epsilon = 1$. Let $M \in N$ and choose $n = M$ and $k = M+1$. $|x_n - x_k| = |(-1)^M - (-1)^{M+1}| = 2 \geq \epsilon = 1$

## 6. Midterm topics
* In class, 90 minutes.
* Format is 6 problems, solve any 4 for full credits.
* Content: 
    * Right before series.
    * Before section 2.5 in Lebl.
    * May reuse practice midterm, and/or similar format
* He doesn't like giving surprises. So it is predictable, like easy HW problems or easy propositions proved in class but still testing knowledge of the materials. Will have technique, computation, and definition testing questions (free points). 
* Likely won't take up 90 minutes.
