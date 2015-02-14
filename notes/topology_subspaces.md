---
title: "Topology: subspaces"
---

1. For any topological space $(X, \mathcal{T})$ and any $A \subseteq X$, consider the set $\iota^{\ast} \mathcal{T} := \{\iota_A^{pre}(U) : U \in \mathcal{T} \}$, where $\iota_A: A \to X$ is the inclusion map. Then $\iota_^{\ast} \mathcal{T}$ is a topology for $A$: it clearly includes $\emptyset$ and $A$, the preimage of an arbitrary union is the union of preimages for any function (so it's closed under unions), and for any $B, C \in \mathcal{T}$, $x \in \iota_A^{pre}(B) \cap \iota_A^{pre}(C)$ iff $x \in A \cap B \cap C = \iota_A^{pre}(B \cap C)$, so it's closed under finite intersections. This topology is called the **subspace topology** on $A$, and it's not hard to see that it is exactly the collection of open sets in $\mathcal{T}$ intersected with $A$.

    We can say more than this though. If $\mathcal{S}$ is any topology on $A$ such that the inclusion $\iota_A$ is continuous, then it must be finer than the subspace topology. In other words, the subspace topology is the *coarsest* topology that makes the inclusion continuous. The proof is quite trivial: if the inclusion is continuous, the pre-image of any open set $U$ in $X$ is open in $\mathcal{S}$. But the preimage is just $U \cap A$.

2. The subspace topology on $A \subseteq X$ obeys what Lee calls the "characteristic property" of the subspace, which is that any map $f: Y \to A$ (where $Y$ is some topological space) is continuous iff $\iota_A \circ f$ is continuous. If $f$ is continuous, $\iota_A \circ f$ certainly must be as well since composition of continuous functions is continuous. Conversely, if $\iota_A \circ f$ is continuous, then for any $U$ open in $A$, $U = A \cap V$ for some $V$ open in $X$, so $(\iota_A \circ f)^{pre}(V) = f^{pre}(U)$ is also open in $Y$, proving $f$ is continuous.

    Presumably Lee calls it the "characteristic topology" because the subspace topology is the *unique* topology on $A$ that has this property. If $A$ equipped with some topology $\mathcal{S}$ has the property that for any $Y$, $f: Y \to A$ is continuous iff $\iota_A \circ f$, by letting $f$ be the identity on $A$ (with same topology $\mathcal{S}$), we can see that $\iota_A$ is continuous, so $\mathcal{S}$ is finer than the subspace topology by (1). 

    Conversely, consider $\phi: A \to A_S$, where $A_S$ is denoting $A$ with the topology $\mathcal{S}$ (this is technically an abuse of notation/nonsense, but it is suggestive!) and $A$ just denotes $A$ with the subspace topology. Then $\iota_A \circ \phi = \iota_A$, which is certainly continuous because $A$ is a subspace. By the characteristic property of $(A, \mathcal{S})$, this means $\phi$ is continuous, which implies (see basic topology notes) that the subspace topology is finer than $\mathcal{S}$. In other words, $\mathcal{S}$ *is* the subspace topology.

3. There are a couple notions of continuous maps that we can now define with subspaces. 

     A **topological embedding** is an injective continuous map $f: X \to Y$ such that the codomain restriction $X \to f(X)$ is a homeomorphism (where $f(X)$ is a subspace of $Y$).

     A **local homeomorphism** is a function $f: X \to Y$ such that for every $x \in X$ there is a neighborhood $U$ of $x$ with 

     - $f(U)$ open in $Y$
     - the two-sided restriction of $f$, $F: U \to f(U)$, is a homeomorphism

4. We can also characterize continuous maps locally: if $f: X \to Y$ and for every $x \in X$, there is a neighborhood $U_x$ of $x$ such that $f|U_x$ is continuous, then for every $V$ open in $Y$, $f^{pre}(V) \cap U_x$ is open in $U_x$, so $f^{pre}(V) \cap U_x \cap V_x$ is open in $X$ for some $V_x$ open in $X$. If we union these up for all $x$ we get $f^{pre}(V)$ being open.

    The converse is obviously true as well.


4. Above we've proved that the inclusion of a subspace into its superspace is continuous. It's also clearly injective, and what's more if we restrict the codomain to the image we just get the identity map on $A$. So the inclusion defined on a subspace is actually a topological embedding.

5. The restriction $f|S: S \to Y$ of any continuous map $f: X \to Y$ to a subset $S \subseteq X$ is still continuous due $(f|S)^{pre}(V) = f^{pre}(V) \cap S$, which is open by definition of the subspace.

6. The closed subsets in a subspace topology on $A \subseteq X$ are exactly the closed subsets of $X$ intersected with $A$. Proof: $C$ is closed in $A$ iff $A - C$ is open iff $A - C = V \cap A$ for some $V$ open in $X$ iff $C = (X - V) \cap A$.


7. We can talk about transitivity of open and closed sets w.r.t. subspaces: if $U$ is open/closed w.r.t. a subspace $A$ that is open/closed in some space $X$, then $U$ is open/closed in $X$. This is because

    - the intersection of two open/closed sets is again open/closed
    - the subspace's open/closed sets are intersections of open/closed sets in $X$ with $A$

8. Here it is, that moment you've been waiting for: the gluing lemma(s?). If we have either:

     - $B_1, \ldots, B_n$ is a finite closed (w.r.t. $X$) cover of $X$
     - $\{B_i\} is an open (w.r.t. $X$) cover of $X$

    And for each cover element $B_i$ we have a map $f_i: B_i \to Y$ that is continuous, such that for each $i$ and $j$, $f_i$ and $f_j$ are the same on the restriction to $B_i \cap B_j$, then there's a unique continuous map $f: X \to Y$ such that $f|B_i = f_i$ for all $i$.

    *Proof:* In either case, for all $x \in X$, pick an $i$ such that $x \in B_i$. Then define $f(x) = f_i(x)$. This is not only well-defined since $f_i(x) = f_j(x)$ when $x \in B_i \cap B_j$, but $f$ is the only such way to have $f|B_i = f_i$ for all $i$.

    In the case of a finite closed cover we have

    $$f^{pre}(C) = \bigcup_{i=1}^n f_i^{pre}(C)$$

    which, in the case of closed $C$, is a finite union of closed sets (since each $f_i$ is continuous), hence closed in $X$.

    In the case of an open cover we have

    $$f^{pre}(U) = \bigcup_i f_i^{pre}(U)$$

    which, in the case of open $U$, is a union of open sets, hence open in $X$.

9. The subspace $A$ of any Hausdorff space $X$ is also Hausdorff because for any two points in $A$ and any disjoint neighborhoods $U, V$ for the points in $X$, when you intersect $U$ and $V$ with $A$ they're still disjoint (and still neighborhoods, obv.)


