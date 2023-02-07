# 18.100P Lecture 1 Quantifiers and Basic Set Theory
[toc]
## 1. Logistics
* Mat Rosenzwag, mrosenzw@mit.edu
* Recitations are mandatory but lectures are not.

## 2. Course Structure
### A) Grading Scheme
* PSETs 40%, due Mondays @11:59PM EST, submit via Gradescope. Drop lowest, 8 out of 9.
* Three communication assignments 35%.
* Two in-class midterm 15%, serving as a check of comprehensing materials.
    * March 16, April 20.
* Recitation attendence 10%.

### B) Course Goals
* **Goal**: explain why calculus works, starting from logics and set theory, then building up in a mathematically rigorous fashion. 
* The essential of the course is how to write a *proof*. No expectation of prior proof class experience. The math is secondary - learning how to write proof is primary.


## 3. Logical Quantifiers
* Universal quantifier: $\forall$ reads "for all"
* Existential quantifier: $\exists$ reads "there exists (at least one)"
* $P \Rightarrow Q$ means "P implies Q"
* $P \Leftrightarrow Q$ means "P imlies Q and Q implies P, or P is True iif Q is True".
### Examples: True or False?
1. $\forall$ real numbers $x$, $x^2 \geq 0$. [True]
2. $\forall$ real numbers $x$, $x > 0$. [False, any real negative numbers!]
3. $\exists$ real number $x$, s.t. $x^2 <0$ [False, contradict #1]
4. $\exists$ real number $x$, s.t. $x > 0$. [True, take 1 for instance]

## 4. Negation of a logical statement
* $\neg P$: The negation of a statement $P$ is the logical complement/opposite of $P$. 
* In other words, $\neg P$ is True whenever $P$ is False. And, $\neg P$ is False whenever $P$ is True.

### Examples: Negate the following
1. Every MIT student likes math. $(P)$
    * $\exists$ MIT student who does not like math. $(\neg P)$
2. There is a car in the parking lot that is blue. $(P)$
    * Every car in the parking lot is not blue. $(\neg P)$
3. $\forall$ real number $x$, $x > 0$. $(P)$
    * $\exists$ real number $x$ s.t. $x \leq 0$. $(\neg P)$ [True]


### Advanced Examples
1. $\forall$ real number $x$, $\exists$ real number $y$ s.t. $x < y$.
    * Proof: given a real number $x$, choose $y = x + 1 > x$.
2.  $\exists$ real number $y$ s.t. $\forall$ real number $x$, $x < y$.
    * False, since $x$ may equal to $y$. Note this is the negation of the first statement. 
    * In other words, there's no number stictly larger than itself.

## 5. Basic Set Theory
* **Defn**: a ***set*** is a collection of objects called members/elements.
* **Defn**: The empty set $\emptyset$ is the set with no elements.
    * $a \in S$ means "$a$ is an element/member of $S$".
    * $a \notin S$ means "$a$ is not an element/member of $S$".

### A) Subset
1.  **Defn**: a set $A$ is a ***subset*** of $B$, denoted $A \subset B$, if $a \in A$ $\Rightarrow$ $a \in B$. In other words, all elments of $A$ are also elements of $B$. 
2.  Two sets $A$ and $B$ are ***equal*** if $A \subset B$ and $B \subset A$. 
3.  $A$ is a ***proper subset*** of $B$, denoted $A \varsubsetneq B$, if $A \subset B$ and $A \neq B$.

### B) Set-Builder Notation
1. $\{x \in A: P(x)\}$ means "all elements $x$ of $A$ satisfies property $P(x)$".
2. We can order the following
    * $N = \{1,2,3,4, \cdots\}$, "Natural numbers"
    * $Z = \{0,1,-1,2,-2, \cdots\}$, "Integers"
    * $Q = \{\frac{m}{n}:m,n \in Z \text{ s.t. } n\neq 0\}$, "Rationals"
    * $R$, "Real numbers"
3. $N \subset Z \subset Q \subset R$ 

### C) Operations between Sets
#### C.1) Definitions. Let $A, B$ be sets:
1.  The **union** of $A$ and $B$ is the set $A \cup B := \{x: x\in A \text{ or } x\in B\}$.
2. The **intersection** of $A, B$ is the set $A \cap B := \{x:x\in A \text{ and } x \in B\}$.
3. The **set difference** of $A, B$ is $A \setminus B := \{x \in A: x\notin B\}$.
4. The **complements** of $A$, denoted by $A^c := \{x:x \notin A\}$.
5. $A$ and $B$ are **disjoint** if $A \cap B = \emptyset$. 

#### C.2) Examples
1. $A \cup B = A\setminus B \cup A \cap B \cup B \setminus A$, which are all mutually disjoint.

#### C.3) True or False
1. $\exists x \in \emptyset$ s.t. $x >0$. [False, because empty set has no element by definition.]
2. $\forall x \in \emptyset, x>0$. [True, vacuously.]

## 6. DeMorgan Theorem (Arithemtics for sets)
Let $A,B,C$ be sets,
 1. $(B\cup C)^c = B^c \cap C^c$
 2. $(B\cap C)^c = B^c \cup C^c$
 3. $A \setminus (B \cup C) = (A\setminus B) \cup (A \setminus C)$
 4. $A \setminus (B \cap C) = (A\setminus B) \cap (A \setminus C)$

**Proof for (1), working off the definitions:**
Recall by definition, two sets $A$ and $B$ are ***equal*** if $A \subset B$ and $B \subset A$. 
Thus we prove $(B\cup C)^c \subset B^c \cap C^c$ and $B^c \cap C^c \subset  (B\cup C)^c$. 

$x \in (B \cup C)^c \Rightarrow x \notin (B \cup C) \Rightarrow x \notin B$ and $x \notin C$, which imples $x \in B^c$ and $x \in C^c$, $\Rightarrow x \in B^c \cap C^c \Rightarrow (B\cup C)^c \subset B^c \cap C^c$.


$x \in B^c \cap C^c \Rightarrow x \in B^c$ and $x \in C^c \Rightarrow x \notin B$ and $x \notin C \Rightarrow x \notin B \cup C \Rightarrow x \in (B \cup C)^c \Rightarrow B^c \cap C^c \subset  (B\cup C)^c$. 

Thus we proved $(B\cup C)^c = B^c \cap C^c$. $\square$

## 7. Set Examples
1. $\{x \in N: x^2 < 6\}$ = $\{1, 2\}$
2. $\{x \in Z: x^2 < 6\}$ = $\{-2, -1, 0, 1, 2\}$
3. $\{x \in R: x^2 < 6\}$ [graph]

![](https://i.imgur.com/xyWdc8s.png)

Which of the following describes the even numbers?
1. $\{x \in Z: \forall y \in Z, x = 2y\}$
2. $\{x \in Z: \exists y \in Z, x = 2y\}$ [This one]




