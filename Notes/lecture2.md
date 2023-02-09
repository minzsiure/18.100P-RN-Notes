# 18.100P Lecture 2
Last lecture, we went over
* Quantifiers $\forall, \exists$
* Logical statements
    * Implications $\Rightarrow, \Leftrightarrow$
    * Negations
* Basic set theory
    * Operations / DeMorgan's Laws

Today,
* Contid
* Principle of Induction

---
[toc]

## 1. Reminder: Set-builder 
$\{x \in A : P(x)\}$

* ie. $\{x \in N : x^2 < 6\} = \{1,2\}$


> What are the following sets?
1. $\{x \in R : \forall y \in [0,1] \text{ s.t. } x < y \}$ = $(-\infty, 0)$
2. $\{x \in R : \exists y \in [0,1] \text{ s.t. } x < y \}$ = $(-\infty, 1)$
3. $\{x \in [0,1] : \forall y \in [0,1] \text{ s.t. } x < y \}$ = $\emptyset$
    * Because this implies $x < x$.
4. $\{x \in [0,1] : \exists y \in [0,1] \text{ s.t. } x < y \}$  = $[0,1)$

---

## 2. Logic conjunction
Conjunctions join two different statements.
### A) Examples
* and: P and Q
* or (inclusive): P or Q
* implies: $P \Rightarrow Q$

### B) Practice
"If you get 80% or more on your first midterm $(P)$, then I will give you \$1 $(Q)$." 

> In which of the following senarios would have I lied?

    a. You get 80% on your test and I give you $1. [No Lie]
    b. You get 70% and I don't give you $1. [No Lie]
    c. You get 100% and I don't give you $1. [Lied; P true, Q false.]
    d. You get 60% and I give you $1. [No Lie]
    e. I give everyone $1 after the grades are out. [No Lie]
    
### C) Contrapositive
* $P \Rightarrow Q$
* The contrapositive is  $\neg Q \Rightarrow \neg P$
* ie. "If I didn't give you \$1, then you didn't get 80% or more on your first midterm."

### D) Bi-implication
* Let $P$ and $Q$ be statements
    * $P \Rightarrow Q$, "$P$ implies $Q$" or "If $P$, then $Q$".
    * $P \Leftrightarrow Q$, "iif", "$P$ implies $Q$ and $Q$ implies $P$" or "If $P$, then $Q$ and If $Q$, then $P$".

> A **mathematical definition** is a bi-implication where a phrase, word, or a symbol on one side is defined with a mathematical statement on the other side.

#### Examples
1. Let $x \in Z$ (integer), x is <u>even</u> iif $\exists k \in Z$ s.t. $x = 2k$.

> You don't need to prove this bi-implication! 
> Because one side is meaningless without the other side.
> On the other hand, you would prove that a given integer is even.

2. Let $z \in Z$. Give a definition for "z is divisible by 4".
    * **Definition:** z is <u>divisible by 4</u> iif $\exists k \in Z$ s.t. $z = 4k$.
3. **Claim:** Let $x \in Z$. If $x$ is even, then $x^2$ is divisible by 4
    * **Proof:** x is even $\Rightarrow$  $\exists k \in Z$ s.t. $x = 2k$. Then  $\exists k \in Z$ s.t. $x^2 = 4k^2$. By definition, $x^2$ is divisible by 4.

---
## 3. Induction
$N = \{1,2,3, \cdots \}$ has an ordering $<$.

### A) Axiom (well-ordering property of $N$):
* If $S \subset N$, then $\exists x \in S$ s.t. $S \neq \emptyset$, $x \leq y$ for any $y \in S$.

### B) Theorem (Induction)
* Let $P(n)$ be some statement depending on a natrual number $n \in N$. Assume 
    1. $P(1)$ is true. [base case]
    2. If $P(m)$ is true, then $P(m+1)$ is true. [inductive step]
* Then $P(n)$ is true $\forall n \in N$.

**Proof**
* Let $S := \{n \in N: P(n) \text{ is not true}\}$
* We want to show $S = \emptyset$ by <u>contradiction</u>.
* Assume for the sake of a contradiction that $S \neq \emptyset$.
* By well-ordering property, $S$ has a least element, denoted by $m \in S$.
* <u>Claim</u>: $m > 1$. 
    * We assumed in Theorem statement $P(1)$ is true. $\Rightarrow 1 \notin S \Rightarrow m > 1$.
* <u>Claim</u>: $m-1 \notin S$.
    * Since $m$ is the least element, and $m-1 < m \Rightarrow m-1 \notin S$.
* $m-1 \notin S$
    * $\Rightarrow P(m-1)$ is true by definition of $S$.
    * $\Rightarrow P(m)$ is true by Assumption (2) of the statement.
    * $\Rightarrow m \notin S$ is a contradiction
* Therefore, $S = \emptyset$. $\square$

### C) Example
> Find all $n \in N$ s.t. $n^2 < 2^n$.
* $n=1, 1<2$ ✔️
* $n = 2, 4=4$ ❌
* $n = 3, 9 > 8$ ❌
* $n = 4, 16 = 16$ ❌
* $n = 5, 25 < 32$ ✔️
* Guess: $n^2 < 2^n$ $\forall n \geq 5$? Attempt by Induction

<u>Base case:</u> $n=5$ ✔️
<u>Inductive step:</u> show $n^2 < 2^n$ for some $n \geq 5 \Rightarrow (n+1)^2 < 2^{n+1}$

<u>LHS: </u>
$(n+1)^2 = n^2 + 2n + 1 < 2^n + 2n + 1$ (by induction hypothesis) $< 2^n + 2n + n = 2^n + 3n < 2^n + n^2$ since $n \geq 5$ $<2^n + 2^n$ (by induction hypothesis) $=2 \cdot 2^n = 2^{n+1}$

<u>RHS:</u> $2^{n+1} = 2 \cdot 2^n$

Done by Principle of Induction $\square$

> Answer: $n=1$ or $n \geq 5$