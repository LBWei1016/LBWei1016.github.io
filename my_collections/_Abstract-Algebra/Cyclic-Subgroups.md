---
layout: page
title: Cyclic Subgroups
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/09/29
---

**Table of Content**
- [Theorem (smallest subgroup of $$G$$)](#theorem-smallest-subgroup-of-g)
  - [Definition (cyclic subgroup)](#definition-cyclic-subgroup)
  - [**Definition (cyclic group)**](#definition-cyclic-group)
  - [Definition (order)](#definition-order)
  - [Theorem (order)](#theorem-order)
  - [Theorem (infinite cyclic groups)](#theorem-infinite-cyclic-groups)
  - [Theorem (finite cyclic group)](#theorem-finite-cyclic-group)
    - [Corollary (the order of an element)](#corollary-the-order-of-an-element)
  - [Problem (determine whether cyclic)](#problem-determine-whether-cyclic)
- [Theorem (subgroups of cyclic groups)](#theorem-subgroups-of-cyclic-groups)
  - [Proof](#proof)
  - [Corollary](#corollary)
  - [Theorem (subgroups of finite cyclic groups)](#theorem-subgroups-of-finite-cyclic-groups)
    - [Corollary $$\\rm I$$ (equality of subgroups)](#corollary-rm-i-equality-of-subgroups)
    - [Corollary $$\\rm II$$ (generators)](#corollary-rm-ii-generators)
    - [Corollary $$\\rm III$$ (number of subgroups)](#corollary-rm-iii-number-of-subgroups)
    - [Corollary $$\\rm IV$$ (order of subgroups)](#corollary-rm-iv-order-of-subgroups)
- [Reference](#reference)

---

## Theorem (smallest subgroup of $$G$$)
Let $$G$$ be a group and let $$a \in G$$. Then 

$$H = \{a^n | n \in \mathbb{Z}\}$$

is a subgroup of $$G$$ and it is the **smallest subgroup of $$G$$** that contains $$a$$, i.e. every subgroup containing $$a$$ contains $$H$$.

> identity: $$a^0 = e$$; inverse: $$a^{-n}a^n = e$$

> 為什麼是 **smallest**？因為封閉性。

### Definition (cyclic subgroup)
> Let $$G$$ be a group and $$a \in G$$. Then the subgroup $$\{a^n:n\in \mathbb{Z}\}$$ is called the **cyclic subgroup generated by $$a$$**, and denoted by $$\langle a \rangle$$.

### **Definition (cyclic group)**
> A group $$G$$ is **cyclic** if $$G = \langle a \rangle$$ for some element $$a \in G$$. The element $$a$$ is called a **generator** for $$G$$.

**Generator** for a cyclic group $$G$$ is not necessarily unique. For example, under addition,  $$\mathbb{Z}_n = \langle \bar 1 \rangle = \langle \overline{n-1} \rangle$$.

> **cyclic $$\iff$$ generator**

> Note: **Being cyclic** is a [structural property](../Groups/#structural-properties).

> 也就是說，**generator** 在 *isomorphic groups* 之間必須一一對應。

### Definition (order)
> If $$\langle a \rangle$$ has a finite number of element, then the **order of $$a$$** is the order $$\vert \langle a \rangle \vert$$ of this subgroup; otherwise, we say $$a$$ is of **infinite order**.

> 經過多少次可以回到自己。

### Theorem (order)
> Let $$G = \langle a \rangle$$ be a cyclic group. If $$a^r = a^s$$ for some $$r > s$$. Then $$G$$ contains *at most* $$r - s$$ elements.

**Proof**

Let $$m = r - s$$. By [Cancellation Law](../Groups/#cancellation-law), we have $$a^m = e$$. For any $$n \in \mathbb{Z}$$, by division algorithm, we can write $$n=qm + r$$ with $$0 \leq r < m$$. Then $$a^n = a^{qm+r} = (a^m)^qa^r = a^r$$. Therefore, every element of $$G$$ is equal to one of $$a^0, \cdots, a^{m-1}$$. ◼

### Theorem (infinite cyclic groups)
> Let $$G = \langle a \rangle$$ be an infinite cyclic group. Then $$a^r \not = a^s$$ for all integers $$r \not = s$$. Moreover, $$G \cong \mathbb{Z}$$.

**Proof**

If $$a^r = a^s$$ for some $$r > s$$, applying [this theorem](#theorem-order) would lead to a contradiction.

We can define $$\phi: G \to \mathbb{Z}$$ by $$\phi(a^m) = m$$, which is a group isomorphism. ◼

### Theorem (finite cyclic group)
> Let $$G = \langle a \rangle$$ be a cyclic group of *order $$n$$*. Then $$G = \{a^0, a^1, \cdots, a^{n-1}\}$$ and $$a^0 = a^n = e$$. Moreover, $$G \cong \mathbb{Z}_n.$$

**Proof**

If $$a^r = a^s$$ for some $$n-1 \ge r > s \ge 0$$, applying [this theorem](#theorem-order) would lead to a contradiction.

Now we have $$a^n = a^r$$ for some $$0 \leq r \leq n-1$$. In this case, $$G$$ contains at most $$n - r$$ elements, so we must have $$r = 0$$. 

Next we define $$\phi: G \to \mathbb{Z}$$ by $$\phi(a^k) = \bar k$$. 

> 剩下請自行思考（homomorphism）。

#### Corollary (the order of an element)
> Let $$a$$ be an element of a group $$G$$. Suppose **$$a$$ is of finite order $$n$$**. Then $$a^n = e$$ and $$a^r = a^s \iff r \equiv s \mod n$$.

### Problem (determine whether cyclic)
> Determine whether $$\mathbb{Z}^{\times}_{18}$$ is cyclic.

**Solution**

We have $$\mathbb{Z}^{\times}_{18} = \{\bar 1, \bar 5, \bar 7, \overline {-7}, \overline{-5}, \overline{-1}\}$$; the order of this group is $$6$$. Suppose $$G = \langle a \rangle = \{e, g, g^2, g^3, g^4, g^5\}$$, and the order of the elements are $$1, 6, 3, 2, 3, 6$$, respectively. We now show the order of elements in $$\mathbb{Z}^{\times}_{18}$$:

$$
\begin{align*}
  \bar 1&: \text{order 1} \\
  \bar 5 \to \bar 7 \to \overline{-1} \to \overline{-5} \to \overline{-7} \to \bar 1&: \text{order 6}\\
  \bar 7 \to \overline{-5} \to \bar 1&: \text{order 3} \\
  \overline{-7} \to \overline{-5} \to \overline{-1} \to \bar 7 \to \bar 5 \to \bar 1&: \text{order 6}\\
  \overline{-5} \to \bar 7 \to \bar 1&: \text{order 3}\\
  \overline{-1} \to \bar 1&: \text{order 2}.\\
\end{align*}
$$

We can then correspond each element of $$G$$ to that of $$\mathbb{Z}^{\times}_{18}$$:

$$\{e, g, g^2, g^3, g^4, g^5\} \to \{\bar 1, \bar 5, \bar 7 ,\overline{-1}, \overline{-5}, \overline{-7}\}.$$

Hence we have shown that $$\mathbb{Z}^{\times}_{18}$$ is cyclic. ◼

事實上，$$\vert \mathbb{Z}_{18}^{\times}\vert = 6$$，而且 $$\mathbb{Z}_{18}^{\times}$$ 有 order 為 $$6$$ 的 element，因此 $$\mathbb{Z}_{18}^{\times} \cong \mathbb{Z}_6$$；已知 $$\mathbb{Z}_6$$ cyclic，於是所求也是 cyclic。

> 用這方法，只需找到一個 order 為 6 的 element，不需找出全部的 order。

> *Think*: Suppose $$G$$ is of order $$n$$. If for all $$g \in G$$, $$g^n = e$$. Can we say that $$G$$ is cyclic?

Actually this is false. Suppose $$n = 4$$, we have $$G = \{e, a, b, c\}$$ such that $$a^4 = b^4 = c^4 = e$$. If we let $$a^2 = b^2 = c^2 = e$$, we can discover that there is no single generator in $$G$$. Thus if for all $$g \in G$$, $$g^n = e$$, $$G$$ is **not necessarily cyclic**. (If $$G$$ is indeed cyclic, this always holds, though.)

---

## Theorem (subgroups of cyclic groups)
> A subgroup of a cyclic group is cyclic.

### Proof
Let $$G = \langle a \rangle$$ be a cyclic group, and $$H$$ be a subgroup. If $$H = \{e\}$$, then $$H = \langle e \rangle$$, which is cyclic.

Now suppose $$H \not = \{e\}$$, then $$a^n \in H$$ for some positive integer $$n$$. Let $$m$$ be the smallest positive integer such that $$a^m \in H$$, and set $$c = a^m$$.

We claim that $$H = \langle c \rangle$$.

Since $$\langle c \rangle$$ is the smallest subgroup containing $$c$$, so we have $$\langle c \rangle \subseteq H$$.

Let $$b \in H$$. Since $$H \subset G = \langle a \rangle, b = a^n$$ for some $$n \in \mathbb{Z}$$. By the division algorithm, there exist integers $$q$$ and $$r$$ with $$0 \leq r < m$$ sucht that $$n = qm + r$$.

Now $$a^r = a^{n - qm} = bc^{-q} \in H$$ because $$b, c \in H$$.

By the assumption that $$m$$ is the smallest positive integer such that $$a^m \in H$$ but $$r < m$$, we must have $$r = 0$$. That is , $$b = c^q \in \langle c \rangle$$; $$H \subseteq \langle c \rangle$$.

Hence we have shown **that**

$$H = \langle c \rangle. \tag*{$\blacksquare$}$$

> 具體來想，$$G = \mathbb{Z} = \langle 1 \rangle, H = \langle 5 \rangle$$，在加法之下。

### Corollary
> The *subgroups* of $$\mathbb{Z}$$ under addition are precisely the groups $$n\mathbb{Z}$$ under addition for $$n \in \mathbb{Z}$$.

> $$n\mathbb{Z} = \langle n \rangle$$, under addition.

### Theorem (subgroups of finite cyclic groups)
Let $$G$$ be a cyclic group of **order** $$n$$ generated by $$a$$. Let $$b = a^s$$ and $$d = \gcd(n, s)$$. Then

$$\langle b \rangle = \langle a^d \rangle = \{a^0=e, a^d, a^{2d}, \cdots, a^{n-d}\}.$$

**Proof**

It is sufficient to show that $$a^d \in \langle b  \rangle$$ and $$b \in \langle a^d \rangle$$.

For $$d = \gcd(n, s)$$, there exist integers $$x, y$$ such that $$nx + sy = d$$. Thus, we have $$a^d = a^{nx+sy} = (a^n)^xa^{sy} = (e)^xa^{sy} = b^y \in \langle b \rangle$$. On the other hand, we cand wirte $$s = ds'$$ for some integer $$s'$$. Then $$b = a^s =  (a^d)^{s'} \in \langle a^d \rangle$$. ◼

> 以下的 $$G$$ 都是 **cyclic group** of order $$n$$ generated by $$a$$。

#### Corollary $$\rm I$$ (equality of subgroups)
> $$\langle a^r \rangle = \langle a^s \rangle$$ if and only if $$\gcd(n, r) = \gcd(n, s)$$.

#### Corollary $$\rm II$$ (generators)
> The other generators of $$G$$ are the elements of the form $$a^r$$, where $$\gcd(n ,r) = 1$$.

#### Corollary $$\rm III$$ (number of subgroups)
> Every subgroup of $$G$$ is equal to $$\langle a^d \rangle$$ for $$d\vert n$$. Especially, **the number of subgroups** of $$G$$ is equal to **the number of divisors of $$n$$**.

> $$\mathbb{Z}_{12}$$ 有 $$6$$ 個 subgroups。

#### Corollary $$\rm IV$$ (order of subgroups)
> When $$G = \mathbb{Z}_n$$, every subgroup is equal to $$\langle \bar d \rangle$$ for some $$d\vert n$$. Moreover, the **order** of the subgroup is equal to $$n/d$$.

> $$n/d: \{0, d, 2d, \cdots, (n/d-1)d\}$$.

---

## Reference
- [How to show a group is cyclic?](https://math.stackexchange.com/questions/838400/how-to-show-a-group-is-cyclic)