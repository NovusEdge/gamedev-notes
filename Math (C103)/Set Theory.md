## What is a Set?
> [!info] Definition
> 
> A **set** is an unordered collection of distinct elements.

The term "_element_" used here, refers to something that is contained within a set. This can be a number, a string, or even another set.

We use the $\in$ sign to denote if an element is contained within a set. For example: $1 \in \{1,2,3,4\}$ to denote the _belongingness_ of `1` in the set that follows, or $1 \notin \{2,3,4,5\}$ to do the opposite.

There are some special sets that are commonly used throughout math. Here's some of them:

| Set                                                                      | Description                 |
| ------------------------------------------------------------------------ | --------------------------- |
| $\emptyset = \{\}$                                                       | Empty Set                   |
| $\mathbb{N} = \{1,2,3,4,...\}$                                           | Set of all natural numbers  |
| $\mathbb{Z} = \{..., -2, -1, 0, 1, 2, ...\}$                             | Set of all integers         |
| $\mathbb{R} = (-\infty, +\infty)$                                        | Set of all real numbers     |
| $\mathbb{Q} = \{\frac{p}{q}\ ;\ q \neq 0\  \land p, q \in \mathbb{Z} \}$ | Set of all rational numbers |
| $\mathbb{C} = \{a + bi\ ;\ a, b \in \mathbb{R} \land i = \sqrt{-1}\}$    | Set of all complex numbers  |

> [!warning] Note
> One important thing to note is that $\emptyset$ and $\{\emptyset\}$ are NOT the same thing

## Set Operations
Like numbers, sets can also undergo operations (although not in the same sense as we do with numbers). Set operations work on the basis of stuff like inclusion and exclusion. Studying `Venn Diagrams` of sets is a good way to learn about these. 

 > [!note] ***Definition*** 
 > The *Intersection* of 2 sets is denoted as $A \cap B$, where the result is a set of elements contained in both $A$ and $B$.
![[SetTheory_Intersection.png | 300]]

> [!note] ***Definition*** The _Union_ of 2 sets is denoted as $A \cup B$, where the result is a set of elements contained in either $A$ or $B$. 
![[SetTheory_Union.png | 300]]

***Definition***: The _complement_ of a set ($A$) is denoted as $A^{c}$  and is the set of all elements that do NOT belong in $A$.

***Definition***: The _difference_ of 2 sets is denoted as $A - B$ or $A\ \backslash\ B$, and is  the set of elements contained in $A$ but not in $B$. i.e. all elements of $A$ excluding all that belong in $A\ \cap\ B$. 
$$ A-B = A \cap B^{c} $$

***Definition***: The _symmetric difference_ of 2 sets is denoted as $A \Delta B$ and is the set of elements that are contained in exactly one of $A$ or $B$ but not both. 
$$ A\ \Delta\ B\ =\ (A \cup B) - (A \cap B) $$

### Set Equality
If $A$ and $B$ are sets, then $A=B$ precisely when they have the same elements as one another (the order does not matter). This definition may also be referred to as: **axiom of extensionality**.

## Subsets and Supersets

> [!info] ***Definition***
> A set $A$ is a **subset** of another set $B$ if every element of $A$ is also contained in $B$. This is represented by the following notation: $$A \subseteq B$$
Alternatively, we also call the set $B$ (in this example) the _superset of $A$_. 

> [!info] ***Definition***
> A set $A$ is a **strict subset** of $B$ if $A \subseteq B$ and $A \neq B$. We denote this by the following notation: $$A \subset B$$
> The term _proper subset_ may also be used for this.

#### Vacuous Truths
This is a somewhat rare but useful concept to understand. By definition, "_A statement is **vacuously true** if it's true simply because it doesn't actually assert anything_".

One example that pertains to sets is the fact that the empty set is a subset of every set, i.e. for any set $S$ it is always true that $\emptyset \subseteq S$.

> [!info] ***Definition***
> A statement "if $P$, then $Q$" is **vacuously true** if $P$ is always false.

## The Power Set

> [!info] ***Definition***
> We define the power set of a set $S$ as $P(S)$ to be the set of all (possible) subsets of $S$.

For example, if $S =\{1,2\}$ then we write the power set of $S$ as: $$P(S) = \{\emptyset, \{1\}, \{2\}, \{1,2\}\}$$
### Cardinality of a Set

> [!info] ***Definition***
> The **cardinality** of a set is a measure of the size of the set. This is denoted as: $|S|$ or $n(S)$.
> 

> [!hint] Note
> The cardinality of a power set is: $|P(S)| = 2^{|S|}$

## Some Important Formulas

1. $$A \cap (A \cup B) = A \cup (A \cap B) = A$$
2. $$A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$$
3. $$A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$$
4. $A \cup A^{c}= U$ and $A \cap A^{c}= \emptyset$
5. $(A \cap B)^{c}= A^{c}\cup B^{c}$ and $(A \cup B)^{c}= A^{c}\cap B^{c}$














