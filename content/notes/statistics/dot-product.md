---
title: dot product
tags: mathematics, linear-algebra
---

An element-wise multiplication between two equal-sized vectors.

# Proof of $a^Tb=||a|| ||b|| \cos{\theta}$
What we need to know is the law of cosines and the distributive property of two vectors:

- **law of cosines** helps us find the length of a triangle given two other sides of a general triangle (meaning it's not necessarily a right triangle). It states that $$c^2 = a^2 + b^2 - 2ab\cos{\theta}$$
- **distributive property for dot product**: $$||a-b||^2 = (a-b)^T(a-b) = a^2 - 2a^Tb + b^2$$

---

So say we have a triangle with sides $a$, $b$, and $c$. We want to find $c$.

