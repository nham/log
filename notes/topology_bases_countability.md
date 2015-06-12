---
title: "Topology: bases and countability"
---
Related notes: [basic topology](topology_basic.html)

3. Here's one sufficient condition for when a collection of sets is a basis for some topology: if $(X, \mathcal{T})$ is a topological space and $\mathcal{C}$ is any collection of open subsets of $X$, then if for all $U \in \mathcal{T}$ and all $x \in U$ we have some $C \in \mathcal{C} with $x \in C \subseteq U$, then $\mathcal{C}$ is a basis that induces $\mathcal{T}$.

    *Proof:* Clearly $\mathcal{C}$ covers the space. But any intersection of two sets in $\mathcal{C}$ is open, so every point in the intersection has a $\mathcal{C}$-set contained in the intersection.

    To rephrase the above: if $\mathcal{C}$ is a collection of open subsets and every open $U$ is a union of sets in $\mathcal{C}$, then $\mathcal{C}$ is a basis for the topology.

6. $\mathbb{R}^n$ with the Euclidean topology is second countable. An outline of a proof is:

     - $\mathbb{Q}$ is dense in $\mathbb{R}$ by basic properties of the reals
     - $\mathbb{Q}^n$ is countable since it is a finite cartesian product of countable sets
     - the collection of open balls centered at $x \in \mathbb{Q}^n$ with rational radii is countable since it is a countable union of countable sets
     - the sup-norm on $\mathbb{R}^n$ is topologically equivalent to the Euclidean norm, and every open box under the sup-norm contains a point with rational coordinates (using density of $\mathbb{Q}$ in $\mathbb{R}$) so $\mathbb{Q}^n$ is dense in $\mathbb{R}^n$ 
     - from this we get that the collection of open balls centered at rational coordinates with rational radii covers the whole space. Intersections of such balls are clearly open, so the collection is a countable basis for $\mathbb{R}^n$


9. A **neighborhood basis** for point $a \in X$ is some collection $\mathcal{B}$ of neighborhoods of $a$ such that every neighborhood of $a$ contains some $B \in \mathcal{B}$.

10. A space is **first-countable** if every point has a countable neighborhood basis.

11. Any second-countable space is first countable. Let $\mathcal{B}$ be a countable basis for $X$. Then one basis that works for any $a \in X$ is all the sets in $\mathcal{B}$ that are neighborhoods of $a$. It's countable since it's a subset of $\mathcal{B}$, and clearly any neighborhood $U$ of $a$ contains some basis set around $a$.

12. A **cover** for a subset $S$ of some topological space $X$ is any collection of subsets of $X$ whose union is a superset of $S$. An **open cover** is a cover consisting of open sets. A **subcover** is a subcollection of cover elements that still acts as a cover for the set.

13. A space is said to be a **Lindelöf space** if every open cover of the space has a countable subcover. A useful fact (I'm foggy on how useful, exactly) is that every second-countable space is Lindelöf.

    Proof: There is some countable basis for the space, so (WLOG) assume $\mathcal{U}$ is an open cover containing $\emptyset$. For every basis element $B$, we define $U_B$ to be either one of the cover elements that contains that basis element if one such cover element exists, or $U_B = \emptyset$ otherwise. If the collection of $U_B$'s is not a subcover, then for some point $x$, every basis element containing $x$ is not contained in any cover element of $\mathcal{U}$, which contradicts that $x$ is in at least one cover element $U$ and that therefore there is some basis element that is a neighborhood of $x$ and is contained in $U$. So the $U_B$'s are a subcover, and they are countable since we are working with a countable basis.

14. The **subspace basis** for a subspace $A$ of some space $X$ w.r.t. a basis $\mathcal{B}$ is just all the basis element intersected with $A$. This construction is easily seen to be a basis (it obviously covers $A$, and if $U_1 = A \cap V_1, U_2 = A \cap V_2$ for $V_1, V_2 \in \mathcal{B}$, for any $x \in U_1 \cap U_2$ there is a $D \in \mathcal{B}$ such that $x \in D \subseteq V_1 \cap V_2$, so $x \in D \cap A \subseteq U_1 \cap U_2$.) It generates the subspace the topology because of distributivity: the union of subspace basis elements is actually the intersection of $A$ with a union of basis elements in $\mathcal{B}$, (so every open set in the topology induced by the subspace basis is open in the subspace topology, but also if it's open in the subspace topology, it must be a union of (original) basis elements intersected with $A$, so is open in the subspace basis induced topology).

15. The **product basis** given bases $\mathcal{B}_i$ for spaces $X_i$, $1 \leq i \leq n$ is (predictably) the collection of all products of basis sets. This is indeed a basis, since for every $x = (x_i : 1 \leq i \leq n) \in \prod_1^n X_i$, we can bind basis elements $B_i$ such that $x_i \in B_i$, so $x \in \prod_1^n B_i$. Also, we have:

    $$\prod_1^n B_i \cap \prod_1^n C_i = \prod_1^n (B_i \cap C_i)$$

    For every $x_i \in B_i \cap C_i$, there's a basis set $D_i$ with $x_i \in D_i \subseteq B_i \cap C_i$, so clearly $x \in \prod_1^n D_i \subseteq \prod_1^n (B_i \cap C_i)$.

    To prove that it really induces the product topology, we first note that the product basis is a collection of open sets (a collection of elements of the standard product topology basis, actually!). So if every $\prod_1^n U_i$ is such that every $x \in prod_1^n U_i$ has a product of basis elements $\prod_1^n B_i$ such that $x \in \prod_1^n B_i \subseteq \prod_1^n U_i$, then it follows that the product basis generates the product topology. But this is certainly true, since if $x_i \in U_i$, there is a basis element containing $x_i$ and contained in $U_i$.
