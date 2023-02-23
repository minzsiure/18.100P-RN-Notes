# 18.100P Lecture 5: Order Fields, Abosolute Value, Sequences
###### tags: `18.100P Lectures`
Last class:
* Ordered fields
* Least Upperbound Properties

Today:
* Finish ordered fields
* $\mathbb{R}$ as an ordered field
* Absolute Value
* Sequences

---

## 1. Ordered fields (continue)
* <u>*Proposition.*</u> Let $\mathbb{F}$ be an ordered field with least upperbound property. If $A \subset 
\mathbb{F}$ is nonempty and bounded below $\Rightarrow \inf A$ exists in $\mathbb{F}$. 
*Proof.* By definition of bounded below, $\exists a \in \mathbb{F}$ s.t. $\forall x \in A, a \leq x$.

> The main trick is to invert the relationships by multiplying by -1, then in the end, undo by multiplying -1 again.

* *Claim.* $B := \{-x : x \in A\}$. $B$ is bounded above.
*Proof.* (Need to check $\exists b \in \mathbb{F}$ s.t. $\forall y \in B, y \leq b$.) $\forall a \in A, a \leq x \Leftrightarrow \forall a \in A, -x \leq -a \Leftrightarrow \forall y \in B, y \leq -a$ 
Nonempty and bounded above by $-a$.

* $\mathbb{F}$ has least upperbound property $\Rightarrow c= \sup B$ exists in $\mathbb{F}$. 
    * By definition of $\sup$, $c \leq -a$.
    * $\forall y \in B, y \leq c \Leftrightarrow \forall x \in A, -x \leq c \Leftrightarrow \forall x \in A, -c \leq x \Rightarrow$ $-c$ is a lowerbound for $A$.
* Remains to show $\forall$ lowerbound $m$ of $A$, $m \leq -c$.
    * Suppose $m$ is a lowerbound of $A \Leftrightarrow -m$ is an upperbound for $B \Rightarrow -m \geq c$ by definition of $\sup$. 


## 2. $\mathbb{R}$ as an ordered field
* $\mathbb{Q}$ has some undesired feature, i.e. doesn't have a least upperbound.

***Theorem.*** There exists a "unique" ordered field, denoted $\mathbb{R}$, s.t. $\mathbb{Q} \subset \mathbb{R}$ and $\mathbb{R}$ has the least upperbound property.
* **Q:** suppose we have $x,y \in \mathbb{R}$ with $x < y$. Does $\exists r \in \mathbb{Q}$, s.t. $x < r < y$?
* **A:** Yes, by density of rational numbers.

### A) Archimedian Property and Density of $\mathbb{Q}$
1. (Archimedian Property) If $x,y \in \mathbb{R}$ and $x > 0$, then $\exists n \in \mathbb{N}$, s.t. $nx > y$.
2. (Density of $\mathbb{Q}$) If $x,y \in \mathbb{R}$ and $x < y$, then $\exists r \in \mathbb{Q}$, s.t. $x < r < y$.

*Proof.*
1. Argue by contradiction. $\forall n \in \mathbb{N}$, $nx \leq y \Leftrightarrow n \leq \frac{y}{x} \Rightarrow \mathbb{N}$ bounded above by $\frac{y}{x}$.
Apply least upperbound property of $\mathbb{R}$ to $\mathbb{N} \Rightarrow a = \sup \mathbb{N}$ exists in $\mathbb{R}$.
Since $a$ least upperbound, $a-1$ is not an upperbound for $\mathbb{N} \Leftrightarrow \exists m \in \mathbb{N}$, s.t. $a-1 < m \Leftrightarrow a < m + 1 \in \mathbb{N}$. #
Conclude $\exists n \in \mathbb{N}$ s.t. $n \geq \frac{y}{x}$.

2. Consider three cases.
Case 1: $0 \leq x < y$.
Case 2: $x < 0 < y$. Trivial, take $r = 0$.
Case 3: $x < y \leq 0$.

<u>Case 1:</u> By Archimedian Property, $n(y-x) > 1$, $\exists n \in \mathbb{N} \Rightarrow ny > nx + 1$. By Archimedian Property, $\exists l \in \mathbb{N}$, s.t. $l > nx$.
$S := \{k \in \mathbb{N}. k > nx\} \neq \emptyset$ because contains $l$.
By well-ordering principle, $S$ has a least element $m \in S \Rightarrow m > nx \Leftrightarrow x < \frac{m}{n}$.
Since $m$ is "least", $m-1 \notin S \Rightarrow m - 1 \leq nx \Leftrightarrow m \leq nx + 1 < ny \Rightarrow \frac{m}{n} < y$.
$\Rightarrow x < \frac{m}{n} < y$.

<u>Case 3:</u> We claim we can convert case 3 to case 1. $x < y \leq 0 \Leftrightarrow 0 \leq -y < -x$ Let $\tilde{x} = -y, \tilde{y} = -x$, s.t. $\tilde{x} 

### B) 
*Proposition.* Suppose $S \subset \mathbb{R}$ nonempty and bounded above. Then $x = \sup S$ iff
1. $x$ is an upperbound for $S$;
2. $\forall \epsilon > 0$, $\exists y \in S$, s.t. $x - \epsilon < y \leq x$.

*Proof.* PSET

## 3. Absolute Value
Definition: If $x \in \mathbb{R}$, 
$$|x| :=
\begin{cases}
x & x \geq 0,\\
-x & x < 0\\
\end{cases}
$$
*Proposition.*
1. $|x| \geq 0$ and $|x| = 0 \Leftrightarrow x = 0$.
2. $\forall x, y \in \mathbb{R}$, $|x \cdot y| = |x| \cdot |y|$.
3. $\forall x \in \mathbb{R}$, $|-x| = |x|$.
4. $|x^2| = x^2 = |x|^2$.
5. $x,y \in \mathbb{R}, |x| \leq |y| \Leftrightarrow -y \leq x \leq y$.
6. $x \leq |x|$.

*Theorem (triangle inequality).* $\forall x,y \in \mathbb{R}$, $|x + y| \leq |x| + |y|$.
*Proof.* 
Let $x,y \in \mathbb{R}$. $x+y \leq |x| + |y|$ by (6).
$(-x) + (-y) \leq |-x| + |-y|$ again by (6).
By (3), $-(x+y) = (-x) + (-y) \leq |-x| + |-y| = |x| + |y|$.
$\Leftrightarrow x+y \geq -(|x| + |y|)$.
By (5), $-(|x| + |y|) \leq x+y \leq |x| + |y| \Leftrightarrow |x+y| \leq |x| + |y|$.



## 4. Sequences
**Definition:** A sequence of real numbers is a function $x: \mathbb{N} \rightarrow \mathbb{R}$. We denote $x(n) = x_n$, and we dentoe the sequence by $\{x_n\}_{n=1}^{\infty},$ or $x_n$, or $x_1, x_2, \dots$.

**Definition:** A sequence $\{x_n\}$ is **bounded** if $\exists B \geq 0$, s.t. $\forall n, |x_n| \leq B$.
$\Leftrightarrow \{x_n:x \in \mathbb{N}\}$ is a bounded set.

**Example:**
* Harmonic sequence, $\{\frac{1}{n}\}$.
    * Claim: bounded by 1.
* $\{n\}$ is not bounded. ($\mathbb{N}$ not bounded)


Remember, <u>a sequence is different from a set</u>.
* i.e. $\{x_n\} = 1, -1, 1, -1, \dots$, $S_n = \{1, -1\}.$ 
