1. A topological space $X$ is said to be **locally Euclidean of dimension $n$** if every $x \in X$ has a neighborhood $U$ that is homeomorphic to an open subset of $\mathbb{R}^n$. A pair $(U, \phi: U \to V)$ where $\phi$ is a homeomorphism and $V$ is open in $\mathbb{R}^n$ is called a **coordinate chart** or just **chart** on $X$. The set $U$ is called the **coordinate domain**. One way of restating the definition of "locally Euclidean of dimension $n$" is saying each point is contained in the domain of some coordinate chart. If $(U, \phi)$ is a chart and $\phi(p) = 0$, we say that the chart is **centered at $p$**. For any chart $(U, \phi)$ and any $p \in U$, we can make a chart on $U$ that has $p$ as its center by translating $\phi(U)$.

    Given any coordinate chart $(U, \phi)$, $U$ is said to be a **coordinate neighborhood** of its points. If $\phi(U)$ is an open ball, then $U$ is said to be a **coordinate ball**.

2. A space $X$ is locally Euclidean of dimension $n$ iff every point in $X$ has a neighborhood homeomorphic to (an open ball in | all of) $\mathbb{R}^n$. The notes on the topology of the reals establish that any two open balls are homeomorphic as well as that any open ball is isomorphic to all of $\mathbb{R}^n$. Also, clearly if a space has every point with a neighborhood homeomorphic to an open ball in $\mathbb{R}^n$, it is locally Euclidean. So it suffices to prove that any locally Euclidean space has each point with a neighborhood homeomorphic to open balls as well.

    So if $X$ is locally Euclidean of dimension $n$, for each $x \in X$, there is some neighborhood $U$ of $x$ such that some homeomorphism $f: U \to f(U)$ exists, where $f(U)$ is open. Now there must be some open ball $B$ centered at $f(x)$ and contained in $f(U)$ because $f(U)$ is open, and its pre-image $f^{pre}(B)$ is a neighborhood of $x$ since $f$ is continuous. So the restriction of $f$ to $f^{pre}(B) \to B$ is again a homeomorphism

3. If $X$ and $Y$ are homeomorphic, then $X$ is locally Euclidean of dimension $n$ iff $Y$ is. In other words, "locally Euclidean" is a topological property. To see this, note that if $X$ is locally Euclidean, then for every $x \in X$, there is a neighborhood $U_x$ that is homeomorphic to an open subset $V_x$ of $\mathbb{R}^n$. Since $X$ and $Y$ are homeomorphic, let $\phi: X \to Y$ be a homeomorphism. Now suppose that $y \in Y$ is arbitrary. Then $x := \phi^{-1}(y)$ has a neighborhood $U_x$ homeomorphic to $V_x \subseteq \mathbb{R}^n$, so $\phi(U_x)$ is a neighborhood of $y$ homeomorphic to $U_x$ and hence to $V_x$.

4. Any open subset $A$ of a locally Euclidean space $X$ is also locally Euclidean of the same dimension. This is because when you restrict the charts on $X$ to the intersections of their domains and $U$, you get another homeomorphism *where the image is open*. This fails for general subsets: the restriction of $\phi: U \to V$ to $A \cap U \to \phi(A \cap U)$ is still a homeomorphism, but $\phi(A \cap U)$ is not necessarily open still. This is true, however, if $A$ is open.

5. A **topological manifold of dimension $n$** (according to Lee) is a second-countable, Hausdorff space that is locally Euclidean of dimension $n$.

6. Being a manifold is a topological property. If $X$ and $Y$ are homeomorphic, then individually we have

     - $X$ is second-countable iff $Y$ is
     - $X$ is Hausdorff iff $Y$ is
     - $X$ is locally Euclidean of dimension $n$ iff $Y$ is

    So that we have $X$ is a topological manifold iff $Y$ is.

7. The first example of a topological manifold of dimension $n$ is $\mathbb{R}^n$ itself: elsewhere in the notes it is proved that $\mathbb{R}^n$ is second-countable, it is certainly Hausdorff (being a metric space), and it is homeomorphic to itself. More generally, any open subset of $\mathbb{R}^n$ is a topological manifold of dimension $n$, since subspaces of Hausdorff/second-countable spaces are Hausdorff/second-countable.

    Another large class of examples: any open subset of a manifold is again a manifold (as a subspace).

8. If $U$ is an open subset of $\mathbb{R}^n$ and $f: U \to \mathbb{R}^k$ is a continuous map, then the graph of $f$, denoted

    $$\Gamma(f) := \{(x, y) \in \mathbb{R}^n \times \mathbb{R}^k : x \in U, y = f(x)\}$$

    is a topological manifold of dimension $n$ when considered to have the subspace topology relative to $\mathbb{R}^n \times \mathbb{R}^k$. (Defining $\Gamma(f)$ is really only done for emphasis, since set-theoretically a function is defined to *be* it's graph set). It is second countable and Hausdorff because the finite product of second-countable Hausdorff spaces is second-countable Hausdorff, and because $\Gamma(f)$ is a subspace of a second-countable Hausdorff space.

    To prove that $\Gamma(f)$ is locally Euclidean of dimension $n$, note that $\phi: \Gamma(f) \to U$ defined by $\phi(x, y) := x$ is a restriction of the projection $\mathbb{R}^n \times \mathbb{R}^k \to \mathbb{R}^n$, so $\phi$ is continuous. It is also bijective since it has an inverse: $\phi^{-1}(x) := (x, f(x))$.

9. The **$n$-sphere** for any $n$ is the collection of points in $\mathbb{R}^{n+1}$ that are distance $1$ away from the origin:

    $$\mathbb{S}^n := \{x \in \mathbb{R}^{n+1} : |x| = 1\}$$

    Familiar examples of $n$-spheres include the $1$-sphere, also known as the unit circle, and the $2$-sphere, also known as the unit sphere in $\mathbb{R}^3$.

    Being a subspace of a second-countable Hausdorff space, the $n$-sphere is also second-countable Hausdorff. To prove that it's a topological manifold of dimension $n$, it remains to prove it is locally Euclidean of dimension $n$.

    Let's write $\mathbb{B}^n$ for the open ball of radius $1$ centered at $0$ in $\mathbb{R}^n$. Consider the function $f: \mathbb{B}^n \to \mathbb{R}$ defined by

    $$f(u) := \sqrt{1 - |u|^2}$$

    Since $0 \leq |u| < 1$, we have $0 < f(u) \leq 1$. Also $f(u) = f(v)$ implies $|u| = |v|$. So the fibers of $f$ are circles of radius $\delta$, $0 \leq \delta < 1$. So the preimage of any open interval $(a, b)$ under $f$ is all the points whose magnitudes lie (strictly) between $\sqrt{1 - b^2}$ and $\sqrt{1 - a^2}$. This is open, so $f$ is continuous. That means the graph of $f$, $\Gamma(f)$, is a topological manifold of dimension $n$.

    Now consider

    $$U_i^+ := \{x \in \mathbb{R}^{n+1} : x_i > 0\}$$

    and

    $$U_i^- := \{x \in \mathbb{R}^{n+1} : x_i < 0\}$$

    For $1 \leq i \leq n + 1$. These are open sets in $\mathbb{R}^{n+1}$, so each $U_i^{\pm} \cap \mathbb{S}^n$ is open in $\mathbb{S}^n$. We can consider each $U_i \cap \mathbb{S}^n$ to be the graph of $f_i^{\pm}: \mathbb{B}^n \to \mathbb{R}$ by defining

    $$f_i^{\pm}(x_j : 1 \leq j \leq n + 1, j \neq i) := \pm \sqrt{1 - \sum_j x_j^2}$$

    So we have this collection $U_i^{\pm} \cap \mathbb{S}^n$ of open sets that cover $\mathbb{S}^n$, and each of them is homeomorphic to an $n$-manifold. Effectively what we've proved is that each point in $\mathbb{S}^n$ has a neighborhood that is homeomorphic to a space that is locally Euclidean of dimension $n$. This means that every point has a neighborhood that is locally Euclidean of dimension $n$, which establishes that $\mathbb{S}^n$ is locally Euclidean of dimension $n$.

10. The **real projective space of dimension $n$** is set defined in the following way: We first take $X := \mathbb{R}^{n+1} - \{0\}$, and then define an equivalence relation on $X$ by $a \sim b$ iff there is a $\lambda \neq 0$, $a = \lambda b$. Then $\mathbb{R} \mathbb{P}^n := X / \sim$, and it has the quotient topology determined by $q: X \to \mathbb{R} \mathbb{P}^n$ where $q$ is the natural projection. A special case of this, $\mathbb{R} \mathbb{P}^2$, is called the **projective plane**.

    (I think $\mathbb{R} \mathbb{P}^n$ is metrizable, with a metric defined by the angle between two lines. This means that open balls in $\mathbb{R} \mathbb{P}^n$ can be thought of as "open cones". Don't know how to make this rigorous).

    $\mathbb{R} \mathbb{P}^n$ is a topological manifold. For each $i = 1, \ldots, i+1$, let $A_i$ be all points in $X$ such that $x_i \neq 0$, and let $U_i := q(A_i)$.

    TODO

11. Lemma 1.10 from Lee says that every topological manifold has a countable basis of precompact coordinate balls.

    Let $X$ be a manifold and $\phi: U \to V \subseteq \mathbb{R}^n$ be a chart on $X$. Let $\mathcal{B}$ be all the open balls $B(q; r)$ such that

     - $r$ is rational
     - $q$ has rational coordinates
     - there exists some $s$ such that $r < s$ and $B(q; s) \subseteq V$.

    Let $\mathcal{C}$ be the balls of rational radius centered at points with rational coordinates. It is a basis for $\mathbb{R}^n$, so let $\mathcal{D}$ be the subspace basis for $V$ induced by $\mathcal{C}$. Every set in $\mathcal{D}$ is an open subset of $\mathbb{R}^n$, so for every $D \in \mathcal{D}$, every $x \in D$ has a $B(q; r) \in \mathcal{C}$ such that $x \in B(q; r) \subseteq D$. Now just pick an $s$ such that $d(x, q) < s < r$, and let $B_x := B(q; s)$. $B_x$ is a set in $\mathcal{B}$, so we've just proven that each such $D$ is a union of sets in $\mathcal{B}$. This proves that $\mathcal{B}$ is a basis for $V$, meaning $V$ has a countable basis of precompact sets. The inverse images of basis sets in $\mathcal{B}$ is then a basis for $U$, they are coordinate balls, and they are all precompact because homeomorphism preserves precompactness.

    Now $X$ is covered by charts, and because $X$ is second-countable it must be Lindelöf, so there is a countable collection of charts that cover $X$. We have just proved that each coordinate domain has a countable basis of coordinate balls that are precompact w.r.t. the domain. Let $A$ be one of these precompact coordinate balls for some domain $U$. Then $\text{clo}_U(A)$ is compact in $X$, which is Hausdorff, so $\text{clo}_U(A)$ is closed in $X$. This means $\text{clo}_U(A) = \text{clo}_X(A)$, so $A$ is precompact in $X$ as well. If we union all these precompact coordinate balls, its a countable union of countable sets. It's also a basis, which establishes that every manifold has a countable basis of precompact coordinate balls.

12. Any topological manifold $M$ is locally path-connected, because by the previous lemma there's a basis of coordinate balls, which are locally path-connected.

13. Any topological manifold $M$ has a countable number of connected/path-connected components. Each component is open, and is a connected topological manifold as a subspace.

    *Proof:* The components are open since this is true for all locally path-connected spaces. Therefore they form an open cover. Manifolds are Lindelöf, so there's a countable subcover. But the components partition the space, so there must only be countably many components in the first place.

    This is because there's a countable basis of path-connected sets, and each of these belongs to exactly one component. That is, there's a surjective map from basis elements to connected components, and the basis set is countable. So the collection of components must be countable too.

14. Any topological manifold $M$ is locally compact. This is immediate from Lee's Lemma 1.10 since, since Hausdorff spaces are locally compact iff every point has a precompact neighborhood.
