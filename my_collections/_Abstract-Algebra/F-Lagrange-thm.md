---
layout: page
title: Lagrange's Theorem
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/15
---

**Table of Content**

---

## Lagrange's Theorem
### Theorem (order of a subgroup)

> Let $$H$$ be a subgroup of a finite group $$G$$. Then the order of $$H$$ **divides** the order of $$G$$。

**Proof**

Since $$G$$ is equal to the disjoin union of left cosets of $$H$$ and every left coset has the same cardinality as $$H$$, we have

$$
\vert G \vert = \vert H \vert \times (\text{# of left cosets}).
$$

This proves the theorem.

### Corollary (order of an element)
> The order of an element $$a$$ of a finite group $$G$$ divides the order of $$G$$.

**Proof**

Let $$H=\langle a \rangle$$, and apply Lagrange's Thm.

### Corollary (cyclic)
> Every group $$G$$ of prime order is cyclic.

**Proof**

Let $$g \in G,\ g \not = e$$. We have $$\vert \langle g \rangle \vert$$ divides $$\vert G \vert$$. Since $$\vert G \vert $$ is prime, $$\vert \langle g \rangle \vert$$ is either $$1$$ or $$\vert G \vert$$. The former case is impossible since $$g \not = e$$. Then $$\vert \langle g \rangle \vert = \vert G \vert$$ implies $$\langle g \rangle = G$$, i.e. $$G$$ is cyclic.

---

## Index
### Definition (index of subgroups)
> Let $$H$$ be a subgroup of a group $$G$$. The number of left cosets of $$H$$ is the **index** of $$H$$ in $$G$$, which is denoted by $$[G:H]$$.

### Theorem (absorb)
> Suppose $$K \le H \le G$$, and $$[G:H]$$ and $$[H:K]$$ are finite. Then $$[G:K]=[G:H][H:K]$$.