1. An **interval** of $\mathbb{R}$ is a subset $I$ such that for all $a, b \in I$, $a < x < b$ implies that $x \in I$. This includes as degenerate cases singletons and the empty set.

2. Every interval is connected. *Proof:* We can clearly ignore degenerate cases, they are connected. Suppose $A$ and $B$ are a disconnection of $I$. There is some $a \in A$, $b \in B$. WLOG we assume $a < b$. Then interval $[a, b]$ has to be contained in $I$.
Consider $c := \inf \{ x \in B : a < x \}$, which is valid since $a$ is a lower bound of the set. $c$ has to be a boundary point of $A$ (and $B$), because

     - every open ball centered at $c$ must intersect $A$ (if one did not,it would contradict the definition of $c$ since we could find elements of the set smaller than $c$)

     - every open ball centered at $c$ must also intersect $B$ by definition of infimum (if one did not, we could find a greater lower bound)

    But $A$ and $B$ are open, and so do not contain boundary points. But they also cover $I$, so one of them must contain $c$. This is a contradiction.

3. Conversely, any connected subset $S$ of $\mathbb{R}$ must be an interval. We again neglect the case of $S$ with less than two points. If $S$ is connected and contains $a, b$ with $a < b$ and is missing some $x$ with $a < x < b$, then $(- \infty, x) \cap I$ and $(x, \infty) \cap I$ are together a disconnection of $I$.


4. The monotone convergence theorem says that every monotonically non-decreasing (non-increasing) sequence that is bounded above (below) converges to the least upper bound (greatest lower bound) of the set of terms. If we start out axiomatizing $\mathbb{R}$ with the least upper bound property, this can be proved as follows: the least upper bound $C$ of the term set exists, so we can find terms arbitrarily close to $C$. But the sequence is monotone, so once we find any term within an $\epsilon$, all other terms are as well. So it converges. The same proof works for non-increasing sequences bounded below.


5. A **geometric series** is something of the form $$\sum_0^{\infty} x^k$$ for $0 \leq x < 1$. (Actually it probably works for $-1 < x < 0$ as well, but I don't need them for defining $e$). Each series of this form converges. Clearly this is true for $x = 0$. For $x \neq 0$, the sequence of partial sums 

    $$s_n := \sum_0^n x^k = \frac{1 - x^{n+1}}{1-x}$$

    is true using that one weird trick. The sequence converges since, letting $C := \frac{1}{1-x}$, we have $C - s_n = \frac{x^{n+1}}{1-x} > 0$ for all $n$, meaning $(s_n)$ is monotone increasing and bounded above by $C$. $C$ is also the limit since $(C - s_n) \to 0$ as $n \to \infty$ (owing to $x^{n+1} < x^n$ for all $n$)


6. The **extended real numbers** are the system of numbers you get by adding $\infty, -\infty$ to $\mathbb{R}$. We can extend the ordering on $\mathbb{R}$ so that

    $$-\infty < x < \infty$$

    for all finite $x$. You can also define addition and multiplication and stuff, but I currently don't see the point.


7. The extended reals allow you to do a few things. To start, you can define the least upper bound for non-empty unbounded sets by letting it be $\infty$ (you can see how it works for greatest lower bounds, I'm sure). What's more, you can say that a real sequence **converges to $\infty$** if it grows unboundedly as $n \to \infty$ (similarly for converging to $-\infty$).  This also allows us to formulate the **extended monotone convergence theorem**, which says that *any* monotone sequence converges to a limit, the LUB in the case of monotone nondecreasing and the GLB in the case of monotone nonincreasing.

    We can go one step further on limits and consider sequences of *extended real numbers*, meaning $\infty$ and $-\infty$ are possibly terms of the sequence. Convergence is defined exactly like you expect.


8. The **order limit theorem** for sequences of extended reals says that if $(a_n)$ and $(b_n)$ are sequences of extended reals and $a_n \leq b_n$ for all $n \geq N$ for some $N$, if the sequences converge then $\lim_{n \to \infty} a_n \leq \lim_{n \to \infty} b_n$.

    The proof is simple: if not, the limit $A$ of $(a_n)$ is strictly greater than $B := \lim_{n \to \infty} b_n$, which means we can find a point $k$ after which all terms of $(a_n)$ are strictly greater than terms of $(b_n)$, which is contrary to assumption.


9. Big O notation: if $f$ and $g$ are functions, we say $f \sim O(g)$ at $a \in dom f$ (pronounced "$f$ is Big O of $g$ near $a$") if there is a neighborhood $N$ of $a$ and a positive $C$ such that

    $$|f(x)| \leq C |g(x)|$$

    whenever $x \in N$. What is a neighborhood, you ask? Well, if $a$ is a real number, then it's just some open ball centered at $a$. If $a = \infty$, then it is the collection of points greater than some $x_0 \in \mathbb{R}$.

10. Big O is kinda counter-intuitive. $f(x) = x$ and $g(x) = 10^9 x$ are Big O of each other near $\infty$, for example. Also, $f(x) = x$ and $g(x) = -10^9 x$ are Big O of each other near $\infty$. Another example: $f(x) = 1$ is Big O of $g(x) = 2^x$ because $1 \leq 2^x$ for all $x > 0$ The converse is not true, however.

    If $f \sim O(g)$ at $a$ and $g(x)$ is nonzero in some neighborhood of $a$, then the Big O condition can be rewritten

    $$|\frac{f(x)}{g(x)}| \leq C$$

    for all $x$ in some neighborhood. So the ratio of the functions' output is bounded by some constant. It's not that it *is* constant, it's that it's *no more than constant*.

11. The "peak point lemma" says that any sequence in $\mathbb{R}$ has a monotone subsequence. For any sequence $(x_n)$ let us say that $x_m$ is a "peak term" if it acts as an upper bound for the terms that follow ($x_m \geq x_n$ for all $n > m$). Then any sequence has either infinitely many or finitely many peak terms.

    If there are infinitely many, we can form a subsequence out of them that must be monotone non-increasing. If there are finitely many of them. every term after the last peak term is strictly dominated by some term that comes later (since they all must fail to be peak terms), so we can find a monotone increasing subsequence.

12. When $(x_n)$ is bounded, the peak point lemma has an interesting consequence: we have a bounded, monotone subsequence, hence convergent subsequence by the monotone convergence theorem. In other words, we have just proved the **Bolzano-Weierstrass** theorem for $\mathbb{R}$: every bounded sequence has a convergent subsequence.

13. What's the point of Bolzano-Weierstrass? Seems like a weird thing to care about on the surface, but this has to do with sequential compactness. For every closed, bounded subset $A$ of $\mathbb{R}$, every sequence in $A$ has a convergent subsequence. But $A$ must also contain the limit of the convergent subsequence since it is closed. In other words, $A$, as a subspace of $\mathbb{R}$, is sequentially compact.

14. In the topology notes we proved sequential compactness iff compactness, and we proved that a) compact subsets of Hausdorff spaces are closed and b) compact subsets of metric spaces are bounded. So what we really have is that subset of $\mathbb{R}$ are compact iff they are closed and bounded.

15. Can we extend the Bolzano-Weierstrass theorem to $\mathbb{R}^n$? If so we would have that subsets of $\mathbb{R}^n$ are compact iff they are closed and bounded (all the logic we used above was true for all metric spaces/topological spaces and not specific to $\mathbb{R}$).

    It turns out that we can! See the real inner product space notes and metric space notes for full details, but we have that $(x_n) \to c$ \in $\mathbb{R}^n$ iff each $(x_n^i) \to c_i$ in \mathbb{R}$.

    So if $(x_n)$ is bounded in $\mathbb{R}^n$, then it is contained in some open box in $\mathbb{R}^n$ (by topological equivalence of Euclidean and sup norms), so the sequence $(x_n^1)$ is bounded in $\mathbb{R}$ and hence has some convergent subsequence. If we take this subsequence of the original $(x_n)$, we now have a subsequence of $(x_n)$ whose first component-sequence converges to some $c_1$. Repeat the procedure with each of the other components. The result is a subsequence for which each component sequence converges in $\mathbb{R}$, so the whole sequence converges in $\mathbb{R}^n$.

16. Here's a neat/useful fact about $\mathbb{R}$: every open subset $U$ of $\mathbb{R}$ is the disjoint union of countable open intervals. One proof goes like this: we partition $U$ by defining an equivalence relation $x \sim y$ iff $[\min{x,y}, \max{x,y}] \subseteq U$. It's easy to prove this really is an equivalence relation. Furthermore the equivalence classes are intervals because if $a \sim b$ with $a < b$, for any $x \in U$ with $a < x < b$, by definition $x \in [a, b] \subseteq U$ so $x$ is in the same equivalence class. What's more, they must be *open intervals* because if there's an inclusive end point, that implies that $U$ contains a boundary point, contrary to it being open.

    So we've just shown that $U$ has a partition of open intervals. But it is a basic theorem that between any two real numbers is a rational number. So pick a rational number in each open interval. This gives an injective map from intervals to rationals, proving the collection of partition elements is countable.
