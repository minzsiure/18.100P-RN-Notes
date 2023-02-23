# 18.100P Lecture 4
###### tags: `18.100P`
Last class:
* Cardinality (what it means to have two sets to have the same size - bijection)
* Cantor's Theorem (Power set of a set has a larger cadinality)
* Ordered sets
    * Upper/lower bounds (many)
    * Least upper bound (supremum, just one)
    * Greatest lower bound (infimum, just one)



---

[toc]

## 0. Recap
1. $(E, <)$ - ordered set
    * $b$ is an upperbound for $E$ iff $\forall x \in E, x \leq b$
    * Suppose $b_0$ is an upperbound for $E$, $b_0$ is **least upperbound** for $E$, denoted $b_0 = \sup E$ iff $\forall b$ upperbound of $E$, $b_0 \leq b$.
    * Say $\tilde{b_0}, b_0$ are upperbounds for $E$, $\forall$ upperbounds $b$ of E, $$b \geq b_0 (*), \\ b \geq \tilde{b_0} \,(**)$$.
    Choose $b = \tilde{b_0}$ in (*) $\Rightarrow$ $\tilde{b_0} \geq b_0$
    Choose $b = b_0$ in (**) $\Rightarrow b_0 \geq \tilde{b_0}$ 
    $\Rightarrow b_0 = \tilde{b_0}$
    
2. $\sup E \in E ?$ 
    * $[0,1) = E, \sup E = 1 \notin E$.
    * $\max E := \sup E$ when $\sup E \in E$.

3. $\inf E \in E ?$
    * $\min E := \inf E$ when $\inf E \in E$.

4. How to prove something is the supremum of the set?
    * $E = \{-2, -1, 0, 1, 2\} \subset Z$
    * *Claim*: $\sup E = 2$
    * *Proof.* 
        1. 2 is an upperbound for E, followed by definition of $E$.
        2. $\forall$ upperbound $b$ of $E$, $2 \leq b$.
        $b$ if an upperbound of $E$ $\Rightarrow$ (by definition of upperbound) $b \geq x, \forall x \in E \Rightarrow$ (choose x = 2) $b \geq 2$.
        
5. $E = N \subset Z$
    * ***Claim:*** $\sup E$ DNE.
    * ***Proof.*** Suppose $b \in Z$ upperbound for $E$.
      $b$ upperbound for $E \Rightarrow b \geq 1 \Rightarrow b \in N$.
      Let $\tilde{b} = b+1 > b$. $\tilde{b} \in N$ since $N$ closes under addition. This contradicts assumption $b$ is an upperbound for $E$.
      
    > Recall from definition of ordered set, $E \subset (S, <)$, $E$ is bounded from above in $S$.

    * ***Claim:*** $\inf E = 1.$
    * ***Proof.*** 
        1. 1 is a lowerbound for $E$.
        2. $\forall$ lowerbound $b$ for $E, b \leq 1$, because $1$ is a lowerbound which belongs to $E$.



---
## 1. Least upperbound property
* **Def:** An ordered set $(S, <)$ has the least upperbound (lub) property if for any $E \subset S$ which is nonempty and bounded from above, **$\sup E$ exists in $E$**.

* Nonexample
    * $Q$ does not have the least upperbound property.
    Show that $E = \{q \in Q, q > 0, q^2 < 2\}$ does not have a sup in E.
    
## 2. Ordered fields
### A) <u>Field</u> definition and (non)examples
* **Def:** A set $F$ is a <u>field</u> if it has two operations $+$ and $\cdot$ that obey the following properties
    * A1)  $\forall x,y \in F$, $x + y \in F$.
    * A2) (Commutativity) $\forall x,y \in F$, $x + y = y + x.$
    * A3) (Associative)  $\forall x,y,z \in F$, $(x+y)+z = x+(y+z).$
    * A4) $\exists$ element $0 \in F$, $\forall x \in F, x + 0 = x.$
    * A5) $\forall x \in F$, $\exists y \in F$ s.t. $x + y=0$ (use label $y = -x$).
    * M1) $\forall x,y \in F, xy \in F$.
    * M2) (Commutativity) $\forall x,y \in F, xy = yx$.
    * M3) (Associative) $\forall x,y \in F, (xy) \cdot z = x \cdot (yz)$.
    * M4) $\exists$ element $1 \in F$, s.t. $\forall x \in F, x \cdot 1 = x$.
    * M5) $\forall x \in F \setminus \{0\}$, $\exists y \in F$ s.t. $x \cdot y = 1$ (we label $y = x^{-1}$).
    * D) $\forall x,y,z \in F$, $(x+y)\cdot z = x \cdot y + x \cdot z$.

* **Nonexamples**
    * ***Claim:*** $(Z, +, \cdot)$ is not a field.
    * Given $x \in Z$, $\exists y \in Z$ s.t. $x \cdot y = 1$? No!
    $\Rightarrow$ consider $Q$, which is a field.
    
* **Examples**
    1. $Z_2 = \{0,1\}, 1+1 = 0$. (defined by mod 2)
    2. $Z_3 = \{0,1,3\}$, $c := a + b \mod 3$, $c := a \cdot b \mod 3$.


### B) Simple properties follow from definition
* **[Proposition 1]:** $0 \cdot x = 0$ $\forall x \in F$.
    * ***Proof.*** 
        > Subclaim: $0+0 = 0$ by [A4].
    
        $0 = 0 \cdot x + (-0 \cdot x)$
        $= (0+0) \cdot x + (-0 \cdot x)$
        $= 0 \cdot x + 0 \cdot x + (-0 \cdot x)$ by [D]
        $= 0 \cdot x$ $\square$
        
        
### C) Ordered field
* **Def:** A field $F$ is an <u>ordered field</u> if $F$ is an ordered set (ie. has relation <) and
    * 1. $\forall x,y,z \in F$, $x < y \Rightarrow x + z < y + z$.
    * 2. If $x > 0$, $y > 0$, then $x \cdot y > 0$.
* **Examples**
    * Q is an ordered field.
* **Nonexamples**
    * $Z_2$ is not an ordered field.  
        * Suppose $0 < 1 \Rightarrow 0 + 1 ? 1+1 \Rightarrow 1 > 0$ #
        * Suppose $1 < 0 \Rightarrow 1 + 1 < 0 + 1 \Rightarrow 0 < 1$ #
        
* **[Proposition 1]:** $x > 0$ iff $-x < 0$. *(Proposition 1.1.8 in Lebl)*
    * ***Proof.*** $x \in F$, $x > 0$. Then by [1] in ordered field definition, choose $z = -x$, 
    $-x = 0 + (-x)$ by [A4] $< x + (-x) = 0$ by [A5]
    
* **[Proposition 2]:** Let $F$ be ordered field. Let $x, y \in F$, $x > 0, y < 0$ or $x < 0, y > 0$ $\Rightarrow x \cdot y <0$.
    * ***Proof.*** 
    $x > 0, y < 0$, $\Rightarrow -y > 0$ by [proposition 1]. 
    $x \cdot (-y) > 0$ by [2] in ordered field definition.
    $\Rightarrow x \cdot y < 0$ by [proposition 1].
    The other case follows by symmetry. $(-x) > 0, -y < 0, x \cdot y = (-x) \cdot (-y) < 0$.
    
## D) Least upperbound property $\equiv$ greatest lowerbound property
**Q:** $F$ is an ordered field with least upperbound property, is it true that $F$ has the greatest lowerbound property?
**A:** Yes.

**Theorem:** Let $F$ be an ordered field with the least upperbound property. If $A \subset F$ s.t. $A \neq \emptyset$ and $A$ is bounded below, then $\inf A$ exists in F.
