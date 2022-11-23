---
layout: page
title: Integral Domain and Charateristic
usemathjax: true
tag: Abstract Algebra, Ring, Field
time: 2022/11/15
---

**Table of Content**
- [Motivation](#motivation)
- [Definition (zero divisor)](#definition-zero-divisor)
  - [Example](#example)
  - [Theorem (zero divisors of $$\mathbb{Z}_n$$)](#theorem-zero-divisors-of-mathbbz_n)
    - [Corollary (when $$n$$ is prime)](#corollary-when-n-is-prime)
  - [Theorem (cancellation law)](#theorem-cancellation-law)
    - [Remark](#remark)
- [Definition (integral domain)](#definition-integral-domain)
  - [Reamrk](#reamrk)
  - [Theorem (subrings with unity of a field)](#theorem-subrings-with-unity-of-a-field)
  - [Theorem (fields are integral domain)](#theorem-fields-are-integral-domain)
  - [Theorem (finite integral domains are fields)](#theorem-finite-integral-domains-are-fields)
    - [Corollary ($$\mathbb{Z}_p$$ is a field)](#corollary-mathbbz_p-is-a-field)
- [Characteristic](#characteristic)
  - [Deinition (the characteristic of a ring)](#deinition-the-characteristic-of-a-ring)
  - [Theorem (check unity)](#theorem-check-unity)
  - [Theorem (subring generated by the unity)](#theorem-subring-generated-by-the-unity)
    - [Remark (why define characteristic $$0$$?)](#remark-why-define-characteristic-0)
    - [Corollary (subring)](#corollary-subring)

---

## Motivation
> Do $$ab=0$$ always imply $$a=0$$ or $$b=0$$? 

## Definition (zero divisor)
> A **non-zero** element $$a$$ of a ring $$R$$ is a **zero divisor** if there exists a **non-zero** element $$b$$ such that $$ab = 0$$.

> 把 $$0$$ 因數分解成 $$a$$ 和 $$b$$ 的感覺。

### Example

- $$\bar 2, \bar 3$$ and $$\bar 4$$ are zero divisors in $$\mathbb{Z}_6$$.

> $$M_n(\mathbb{R})$$ 中有很多 zero divisor！

### Theorem (zero divisors of $$\mathbb{Z}_n$$)
> The zero divisors of $$\mathbb{Z}_n$$ are *precisely* the nonzero elements whose representatives are **not relatively prime** to $$n$$.

#### Corollary (when $$n$$ is prime)
> If $$p$$ is a prime, then $$\mathbb{Z}_p$$ has no zero divisors.

### Theorem (cancellation law)
> **The cancellation law** holds for a ring $$R$$ iff $$R$$ has **no** zero divisors.

**Proof**

$$(\Rightarrow)$$ Assume that the cancellation law holds, but $$ab=0$$ for some $$a, b \not = 0$$. Then we have $$ab = 0 = a0$$, but $$b \not = 0$$, which is a contradiction.

$$(\Leftarrow)$$ Assume that $$R$$ has no zero divisors. If $$ab=ac$$ and $$a\not = 0$$, then $$ab-ac=0=a(b-c)$$, by distributive law. Since $$R$$ has no zero divisors and $$a$$ is assumed to be nonzero, we have $$b-c=0$$ and thus $$b=c$$. ◼

#### Remark

- 就算 $$R$$ 有 zero divisors，只要 $$a^{-1}$$ 存在，$$ab=ac$$ 依舊 implies $$b=c$$。

- 如果 $$R$$ 沒有 zero divisor，則當 $$a\not = 0$$， $$ax=b$$ 在 $$R$$ 中至多有一解（$$a(x_1-x_2) = 0 \Rightarrow x_1=x_2$$；可能無解）。

- If $$R$$ is a **commutative** ring with unity and $$R$$ has no zero divisors, for convenience, $$a^{-1}b$$ can be denoted as **$$b/a$$**. In this case, $$a^{-1}$$ is denoted by **$$1/a$$**.

---

## Definition (integral domain)
> A *commutative* ring $$R$$ with unity $$1\not=0$$ and has *no zero divisors* is an **integral domain**.
>
>The ring of integers $$\mathbb{Z}$$ is an integral domain. 

> 如果 $$R$$ 是 integral domain，則 $$R$$ 的結構和 $$\mathbb{Z}$$ 便有些類似！

### Reamrk

- $$\mathbb{Z}_n$$ is an integral domain iff $$n$$ is prime.
- The direct product $$R\times S$$ of two nonzero rings $$R$$ and $$S$$ is never an integral domain since $$(r,0)(0,s)=(0,0) $$ for all $$r\in R$$ and $$ s\in S$$.

> 第二項 remark 說明了，我們難以用 direct product 的方式建構出性質良好的 ring，不像 [groups](../G-Finitely-Generated-Abelian-Groups)。

### Theorem (subrings with unity of a field)
> *Every* **subring** $$R$$ of a field containing the **unity** is an integral domain.

### Theorem (fields are integral domain)
> *Every* field $$F$$ is an integral domain.

**Proof**

Show that for any $$a, b \in F$$ with $$ab=0$$, if $$a\not = 0$$, then $$b=0$$.

### Theorem (finite integral domains are fields)
> *Every* **finite** integral domain $$D$$ is a field.

#### Corollary ($$\mathbb{Z}_p$$ is a field)

From [this corollary](#corollary-when-n-is-prime), $$\mathbb{Z}_p$$ is a field when $$p$$ is a prime.

> Wedderburn's theorem: *every* finite **division ring** is a field.

**Proof**

We have to show that every nonzero element $$a$$ of $$D$$ has a multiplicative inverse. Let $$0, 1, a_1,\cdots ,a_n$$ be all elements of the finite integral domain $$D$$. 

Let $$\phi: D\to D$$ given by $$\phi_a(x) = ax$$, for any $$a,x\in D$$. Then we can see that $$\phi$$ is a permutation since all the products 

$$
a0, a1, aa_1,\cdots,aa_n
$$

are distinct, since $$ab=ac$$ implies $$b=c$$ by Cancellation law. Thus, 

$$
0, a, aa_1, \cdots,aa_n
$$

must be all the elements of $$D$$, and one of them must be $$1$$, i.e. $$aa_i = 1$$ for some $$a_i$$. This proves the theorem. ◼

**Remark**

如果 $$D$$ is *infinite* 呢？設 $$D=\mathbb{Z}, a=2$$， 將 $$\mathbb{Z}$$ 中的全部元素乘上 $$2$$ 之後會得到 $$2\mathbb{Z}$$，但 $$\mathbb{Z}\not = 2\mathbb{Z}$$！

---

## Characteristic
### Deinition (the characteristic of a ring)
> Let $$R$$ be a ring. Suppose that there is a positive integer $$n$$ such that $$n\cdot a = 0$$ for all $$a\in R$$. The least $$n$$ is the **characteristic** of the ring $$R$$. If no such positive integer exists, then $$R$$ is of **characteristic $$0$$**.

> 像是 cyclic group 的 order！

**Example**

1. The rings $$\mathbb{Z}_n$$ are of characteristic $$n$$.
2. The rings $$\mathbb{Z}, \mathbb{Q},\mathbb{R},$$ and $$\mathbb{C}$$ all are of characteristic $$0$$.

### Theorem (check unity)
> Let $$R$$ be a ring with **unity**. If $$n\cdot 1 \not = 0$$ for all $$n\in\mathbb{Z}^+$$, then $$R$$ has characteristic $$0$$. If $$n\cdot 1=0$$ for some $$n\in \mathbb{Z}^+$$, then the smallest such integer $$n$$ is the characteristic of $$R$$.

> 判斷 unity 就夠了！

**Proof**

If $$n\cdot 1\not = 0$$ for all $$n \in\mathbb{Z}^+$$, then $$R$$ is clearly of characteristic $$0$$, by definition.

If $$n\cdot 1=0$$ for some $$n\in \mathbb{Z}^+$$, then for all $$a\in R$$, we have 

$$
n\cdot a = (a+\cdots+a) = a(1+\cdots+1) = a(n\cdot 1) = a0 = 0.
$$

Then the theorem follows. ◼

### Theorem (subring generated by the unity)
> Let $$R$$ be a ring with unity of characteristic $$n$$ (which can be zero). Then $$\langle 1_R \rangle \cong \mathbb{Z}_n$$.

**Proof**

We know that $$\langle 1_R \rangle = \{0, 1_R, 2\cdot 1_R,\cdots ,(n-1)1_R\}$$. Then we can define $$\phi: \langle 1_R \rangle \to \mathbb{Z}_n$$ by 

$$
\phi(a \cdot 1_R) = a,\ a \in \mathbb{Z}_n,
$$

which can be shown to be an isomorphism.

#### Remark (why define characteristic $$0$$?)

應該將 $$\mathbb{Z}_n$$ 視為 quotient ring $$\mathbb{Z}/n\mathbb{Z}$$。因此，當 $$n=0$$，$$\mathbb{Z}/0\mathbb{Z} \cong \mathbb{Z}$$。這就是將 characteristic 定義為 $$0$$ 而非 **infinity** 的原因之一。

#### Corollary (subring)
> *Every* ring with **unity** contains $$\mathbb{Z}$$ or $$\mathbb{Z}_n$$ as its **subring**.