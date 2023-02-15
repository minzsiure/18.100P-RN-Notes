# 18.100P Lecture 3: Functions, Cardinality, and Ordered Sets
###### tags: `18.100P`
UA: Jakin Ng (jakinng@mit.edu) for extensions

Last class
* Logical conjunctions
* Induction

Today
* Functions
* Cardinality
* R as an ordered field w/ least upper bound property

---

## 1. Functions
**Defn:** given sets $A, B$, a function $f:A \rightarrow B$ is a mapping that assigns to each $x \in A$ a unique value $f(x) \in B$.
> A is domain, B is codomain.
<!-- * If $C \subset A$, we define a new set $f(C) := \{y \in B : y = f(x) \text{ for } x \in C\}$ -->
* If $C \subset A$, we define a new set $f(C) := \{f(x) \in B : x \in C\}$
    > $f(C)$ is also called the <u>image</u> of $C$ under $f$.
* If $D \subset B$, we define a new set $f^{-1}(D):=\{x \in A: f(x) \in D\}$
    > $f^{-1}(D)$ is the <u>inverse image/preimage</u> of $D$ under $f$.

**Example**
<div style="text-align:center;">
    <img src="https://i.imgur.com/H5wmlL6.jpg" width="200">
</div>

* $f(\{1,2\}) = \{a\}$, $f^{-1}(\{b\}) = \{3,4\}$


<div style="text-align:center;">
    <img src="https://i.imgur.com/AkOJykx.jpg" width="200">
    not surjevtive/onto
</div>



**Defn:** $f:A \rightarrow B$
1. $f$ <u>injective</u> (one-to-one) iff $f(x_1) = f(x_2) \Rightarrow x_1 = x_2$
    > In other words, $f$ is injective if $\forall y \in B,$ the set $f^{-1}(\{y\})$ is empty or consists of a single element.
3. $f$ <u>surjective/onto</u> iff $f(A) = B$, or $\forall y \in B, \exists x \in A$ s.t. $f(x) = y$
4. $f$ <u>bijective</u> iff both injective and surjective.
5. Suppose $f$ is bijective, then $\exists !$ (a unique map) $f^{-1}: B \rightarrow A$ which is the function that assigns to each $y \in B$, the *unique* $x \in A$ s.t. $f(x) = y$.

![](https://i.imgur.com/WZHfA5p.png)


## 2. Cardinality
### A) Definition
Two sets $A, B$ have the same <u>cardinality</u> iff there exists a *bijection* $f:A \rightarrow B$.

### B) Notation
1. $|A| = |B|$ iff $A$ and $B$ have the same cardinality.
2. $|A| = n$ for some natural number $n$ if $|A| = |\{1, \cdots , n\}|$
    > $A$ if finite with $n$ elements
3. $|A| \leq |B|$ if $\exists$ injection $f: A \rightarrow B$.
4. $|A| < |B$ if $|A| \leq |B|$ but $|A| \neq |B|$


### C) The Cantor-Schroeder-Bernstein theorem
> $x \leq y$ and $y \leq x$ $\Leftrightarrow x = y$
* $|A| \leq |B|$ and $|B| \leq |A| \Rightarrow |A| = |B|$

### D) More definitions
* If $|A| = |ℕ|$, then $A$ is <u>countably infinite</u>.
* If $A$ is finite or countably infinite, then $A$ is <u>countable</u>. 
    * Otherwise, $A$ is <u>uncountable</u>.

#### Examples:
* **Claim (pg17):** $|\{Evens\}|$ = $|\{Odds\}|$ = $|\{ℕ\}|$
    > In other words, we claim the set of even/odd natural numbers has the same cardinality as ℕ.

* ***Proof for $|\{Evens\}|$ = $|\{ℕ\}|$.***
$\{Evens\} = \{2n:n \in ℕ\}$
Define a bijection $f:ℕ \rightarrow \{2n:n \in ℕ\}$ = $\{Evens\}$. $f(n) := 2n$.
    > ***Need to ask in OH about this injective thing
    
    <u>Injective:</u> $f(n) = 2n = 2m = f(m) \Rightarrow n=m$.
    <u>Surjective</u>: Given $m \in \{Evens\}$, need to find $n \in ℕ$ s.t. $f(n) = m$. Since $m$ is even, by definition, $\exists k \in ℕ$ s.t. $m = 2k$. Choose $n = k \Rightarrow f(n) = 2k = m$.


> Remark: turns out that $|ℤ| = |ℕ| = |Q|$.


### E) Power sets
**Q: Is there anything bigger than |ℕ|?**
* **Defn:** given a set $A$, we define the <u>power set</u> of $A$, denoted $𝒫(A) := \{B:B\subset A\}$ 
    > "set of all subsets of $A$"
* Concept check: 
    * $A = \emptyset$. $𝒫(A) = \{\emptyset\}$.
        > a set is always a subset of itself.
    * $A = \{1\}$, $𝒫(A) = \{\emptyset, 1\}$.
    * $A = \{1, 2\}$, $𝒫(A) = \{\emptyset, \{1\}, \{2\}, \{1,2\}\}$
* In general, if $|A| = n$, $|𝒫(A)| = 2^n$.
* **Theorem (Cantor, pg18):** if $A$ is a set, then $|A| < |𝒫(A)|$. 
    > Remark: $|ℕ| < |𝒫(ℕ)| < |𝒫(𝒫(ℕ))| < \cdots$


* **Proof (pg18, need to ask in OH about this proof):**** 
Define $f: A \rightarrow 𝒫(A)$ by $f(x) := \{x\}$. We claim this is injective.
    > $f(x) = f(y) \Rightarrow \{x\} = \{y\}$ and they are subset of each other. $\Rightarrow x \in \{y\} \Rightarrow x=y$.
    
    $\Rightarrow |A| \leq |𝒫(A)|$. 
    
    Want to show $|A| \neq |𝒫(A)|$. Show by contradiction.
    Suppose for the sake of contradiction that $|A| = |𝒫(A)| \Rightarrow \exists$ bijection $g:A \rightarrow 𝒫(A)$.
    Introduce $B := \{x \in A : x \notin g(x)\}$, $B \in 𝒫(A)$.
    Since $g$ is surjective, $\exists b \in A$ s.t. $g(b) = B$.
    
    Case 1: $b \in B$;
    Case 2: $b \notin B$.
    In case 1, $b \in B \Rightarrow b \notin g(b) = B \, \#$.
    In case 2, $b \notin B = g(b) \Rightarrow b \in B$ (by definition of $B$). $\#$
    Thus $|A| \neq |𝒫(A)|$. $\square$
    
## 3. Description of ℝ (real number)
### A) Ordered sets
* **Defn:** an <u>ordered set</u> $(S, <)$ [set, relation] s.t. 
    1. $\forall x,y \in S$, exactly one of $x < y$, $y < x$, $x = y$ holds. (trichotomy, able to compare $x, y$)
    2. If $x < y$ and $y < z$, then $x < z$. (transtivity)
* Examples
    1. ℤ. $m > n$ iff $m-n \in ℕ$.
    2. ℚ. $p > q$ iff $\exists m, n \in ℕ$ s.t. $p-q = \frac{m}{n}$.
* Non-examples
    1. $S = 𝒫(ℕ)$, $A < B$ iff $A \subset B$.
    > $A = \{1\}, B = \{2\}$ doesn't satisfy property (1) in the definition of ordered set.

### B) Bounded sets
* **Defn:** Let $(S, <)$ be an ordered set. Let $E \subset S$.
    1. If $\exists b \in S$ s.t. $x \leq b$ $\forall x \in S$, then $E$ is <u>bounded from above</u> and $b$ an <u>upperbound</u> of $E$.
    2. If $\exists b \in S$ s.t. $x \geq b$ $\forall x \in E$, then $E$ is <u>bounded from below</u> and $b$ an <u>lowerbound</u> of $E$.
    3. $b_0 \in S$ is the <u> least upperbound</u> for $E$ if 
        a. $b_0$ is an upperbound for $E$
        b. $\forall$ upperbound $b$ of $E$, $b \geq b_0$. [least]
        > also call $b_0 = \sup E$ "supermum" 
    4. $b_0 \in S$ is the <u>greatest lowerbound</u> for $E$ if 
        a.  $b_0$ is an lowerbound for $E$
        b. $\forall$ lowerbound $b$ of $E$, $b_0 \geq b$. 
        > also call $b_0 = \inf E$ "infimum" 



---

Next class: order set and order field
    