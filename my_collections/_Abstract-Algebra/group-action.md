---
layout: page
title: Group Action
usemathjax: true
tag: Abstract Algebra, Group
time: 2023/02/13
---

**Table of Content**
- [Definition (Group action)](#definition-group-action)
  - [Remark](#remark)
  - [Example (prove to be a $$G$$-set)](#example-prove-to-be-a-g-set)
  - [Proposition (Group actions as permutations)](#proposition-group-actions-as-permutations)
    - [Remark](#remark-1)
  - [Examples](#examples)
  - [Definition (faithful and transitive)](#definition-faithful-and-transitive)
    - [Remark](#remark-2)
- [Orbit and Stabilizer](#orbit-and-stabilizer)
  - [Definition (orbit)](#definition-orbit)
    - [Lemma (transitive and orbit)](#lemma-transitive-and-orbit)
  - [Definition (stabilizer)](#definition-stabilizer)
  - [Theorem (eq. relation)](#theorem-eq-relation)
    - [Remark](#remark-3)
    - [Corollary (disjoint union of orbits)](#corollary-disjoint-union-of-orbits)
  - [Theorem (the orbit-stabilizer theorem)](#theorem-the-orbit-stabilizer-theorem)

---

## Definition (Group action)
> Let $$X$$ be a set and $$G$$ a group. An **action** of $$G$$ on $$X$$ is a map $$*: G\times X\to X$$ such that 
>
> 1. $$*(e, x) = x$$ for all $$x\in X$$, where $$e$$ is the identity element of $$G$$.
> 2. $$*(g_1, *(g_2, x)) = *(g_1g_2, x)$$ for all $$x\in X$$ and all $$g_1, g_2 \in G$$.
>
> We write $$*(g, x)$$ as **$$gx$$** for simplicity. Thus the above two conditions can be rephrased as:
> 1. $$ex = x$$ for all $$x\in X$$.
> 2. $$g_1(g_2x) = (g_1g_2)x$$ for all $$x\in X$$ and all $$g_1, g_2 \in G$$.

> Under these conditions, $$X$$ is referred to as a **$$G$$-set**.

### Remark

- We say *$$G$$ acts on $$X$$*.
- The second condition has **nothing** to do with *associativity*, since $$g_i$$ and $$x$$ belong to different sets.

### Example (prove to be a $$G$$-set)

See [this](../more-group-action/#proof-y-is-a-g-set).

### Proposition (Group actions as permutations)
> Suppose that a group $$G$$ acts on a set $$X$$. Then for a given $$g\in G$$, **the function $$X\to X$$ represented by $$g$$** is **one-to-one** and **onto**, that is:
> 
> 1. If $$gx_1 = gx_2$$, then $$x_1 = x_2$$.
> 2. For all $$y\in X$$, there exists $$x\in X$$ such that $$gx = y$$.

**Proof** (Ignored.)

> **Q:** Do we must have $$gx \in X$$ for any $$g\in G, x\in X$$?
>
> **A**: Certainly! Since the range of the mapping $$*$$ is $$X$$.

#### Remark

[回想起來](../Cayley-thm)，permutation 是一 **one-to-one** 且 **onto** 的 mapping，與此處的 group action 不謀而和。也就是說，以上的定理可以如下表示：

Let $$S_X$$ be the set of permutations on $$X$$. A group action $$*$$ of $$G$$ on $$X$$ can be regarded as **a group homomorphism** $$\rho: G\to S_X$$ such that

$$
*(g, x) = gx = \rho(g)x,
$$

where $$\rho(g) \in S_X$$ and hence $$\rho(g): X\to X$$. 

於是

$$\text{An action of } G \text{ on } X \iff \text{a group homomorphism from } G \text{ to } S_X.$$

注意，我們討論的是 $$X$$ 的 permutation，是否存在 $$\rho(g_i) = \rho(g_j), i\not =j$$ 並不重要！

> 相當於問 $$g_ix$$ 是否等於 $$g_jx$$。

底下證明 $$\rho$$ 是 group homomorphism：

**Proof**

For all $$g_1, g_2\in G$$, 

$$
\begin{align*}
  *(g_1, *(g_2, x)) &= \rho(g_1)\big(\rho(g_2)x\big) \\
  &= \big(\rho(g_1)\rho(g_2)\big)x \\
  &= *(g_1g_2, x) = \rho(g_1g_2)x. \tag*{$\blacksquare$} \\
\end{align*}
$$

### Examples

Below $$G$$s act on $$X$$s, repsectively.

- Let $$G$$ be a group of symmetries of an object $$X$$.
- Let $$G=S_n$$, $$X=\{1, 2,\cdots, n\}$$.
  - $$S_n$$ acts on $$X$$ by $$\sigma x = \sigma(x)$$.
- Let $$G=\text{GL}(n, \Bbb{R}), X=\Bbb{R}^n$$.
  - $$\text{GL}(n, \Bbb{R})$$ acts on $$X$$ by $$(M, v) \mapsto Mv$$.
- Let $$X=G$$; $$(g, x)\mapsto gx$$. 
  - See [Cayley's theorem](../Cayley-thm).
- Let $$X=G/H$$; $$(g, aH) \mapsto (ga)H$$.
  - See [generalized Cayley's theorem](../more-on-normal-subgroups/#normal-subgroup-and-homomorphism).
- Let $$X$$ be a non-empty set and $$n$$ be a positive integer. Let $$G$$ be *any* subgroup of $$S_n$$.
  - $$S_n$$ acts on $$X^n$$ by $$(\sigma, (x_1, \cdots, x_n)) \mapsto (x_{\sigma(1)}, \cdots, x_{\sigma(n)})$$.
- The map $$*: G\times G\to G$$ given by $$*(g, x) = gxg^{-1}$$ is a group action, since $$\rho: G \to \text{Aut}(G)$$ is a group homomorphism.
  - See [remark](#remark-1) and [Normal Subgroup and Homomorphism](../more-on-normal-subgroups/#normal-subgroup-and-homomorphism).

### Definition (faithful and transitive)
> A group action $$*$$ by $$G$$ on $$X$$ is said to be **faithful** if $$e\in G$$ (identity) is the **only** element that leaves every element of $$X$$ unchanged. That is to say, **$$*$$ is faithful iff $$\text{ker}(\rho) = \{e\}$$**, where $$\rho: G\to S_X$$, by this [remark](#remark-1).
>
> Then, $$*$$ is called **transitive** if for all $$x_1,x_2\in X$$, there exists $$g\in G$$ such that $$gx_1 = x_2$$.

#### Remark 

If $$*$$ is transitive, the [induced homomorphism](#remark-1) must be non-trivial.

> 不 transitive 也可以 non-trivial！存在 $$gx_1=x_2$$ 就代表 $$\rho(g)$$ 不是 identity map。

---

## Orbit and Stabilizer
### Definition (orbit)
> Let $$X$$ be a $$G$$-set. The $$G$$-orbit **of $$x$$** is defined as 
>
> $$
> G_x := \{gx\mid g\in G\}.
> $$

> See [Symmetry Groups on N-gons](../n-gons/#the-order-of-the-symmetry-group). Note that $$G$$-orbit itself is a $$G$$-set.

令 $$H$$ 為 $$G$$ 的 subgroup。若 $$H$$ 作用在 $$G$$ 上，則對於任意 $$g\in G$$，$$H$$-orbit of $$g$$ 就是 $$H$$ 的 [right coset](../coset/#definition-coset)！也就是說，$$H_g = Hg$$。

#### Lemma (transitive and orbit)

>If an action of $$G$$ on $$X$$ is **transitive**, then for any $$x\in X$$, 
>
>$$
>G_x = X.
>$$

**Proof**

By the [definition](#definition-faithful-and-transitive) of transitivity.

### Definition (stabilizer)
> Let $$X$$ be a $$G$$-set. The set $$\text{Stab}_G(x) = \{g\in G\mid gx = x\}$$ for all $$x \in X$$, is called the stabilizer of $$x$$ in $$G$$.

> $$\text{Stab}_G(x)$$ is a **subgroup** of $$G$$.

### Theorem (eq. relation)
> Let $$X$$ be a $$G$$-set. Define a relation $$\sim$$ on $$X$$ by $$x_1\sim x_2$$ if there exists $$g\in G$$ such that $$gx_1 = x_2$$. Then $$\sim$$ is an equivalence relation.

> See [Relation](../../_Concrete-Math/Relation/#equivalence-relation).

#### Remark

The equivalence relation defined above defines a partition of $$X$$, and the cell of $$x\in X$$ is exaclty the **$$G$$-orbit** of $$x$$. Hence, $$X$$ can be written as a **disjoint union of $$G$$-orbits**.

為什麼是 $$G$$-orbit？因為 $$G$$-orbit 收集 $$gx$$，而如果 $$gx = x'$$，那麼 $$x\sim x'$$！

#### Corollary (disjoint union of orbits)
> $$X$$ can be written as a **disjoint union of $$G$$-orbits**.

### Theorem (the orbit-stabilizer theorem)
> For all $$x\in X$$, where $$X$$ is a $$G$$-set, we have $$\vert G_x\vert = [G:\text{Stab}_G(x)]$$. If $$\vert G\vert$$ is finite, we have
>
> $$
> \vert G\vert = \vert G_x\vert \vert\text{Stab}_G(x) \vert.
> $$

> See [Symmetry Groups on N-gons](../n-gons/#theorem-stabilizer--ordit).

**Proof**

We are to show that there is a bijection between $$G_x$$ anf the left cosets $$G/H$$, where $$H=\text{Stab}_G(x)$$.

Let $$\phi: gH\to G_x$$ be the function given by $$\phi(gH) = gx$$. First, we should establish the well-defiinedness of it.

<u>well-definedness</u>

Suppose $$g_1H = g_2H$$, and thus $$g_1 = g_2h$$ for some $$h\in H$$. Then we have $$\phi(g_1H) = g_1x = g_2hx = g_2x = \phi(g_2H)$$, since $$h\in \text{Stab}_G(x)$$ and $$hx = x$$. Therefore $$\phi$$ is well-defined.

Then show $$\phi$$ is bijective.

<u>one-to-one</u>

Suppose that $$\phi(g_1H) = \phi(g_2H)$$. This means that $$g_1x = g_2x \implies g_1^{-1}g_2x = x$$. Hence, $$g_1^{-1}g_2 \in H$$, which implies that $$g_1H=g_2H$$.

<u>onto</u>

Let $$y\in G_x$$ Then $$y=gx$$ for some $$g\in G$$. It follows that $$\phi(gH) = gx = y$$. ◼