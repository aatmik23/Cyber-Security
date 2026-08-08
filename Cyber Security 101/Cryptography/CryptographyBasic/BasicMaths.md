
xor exclusive OR

	differnet 1 same 0


This means A ⊕ A = 0, and A ⊕ 0 = A


commutative, i.e., A ⊕ B = B ⊕ A. And it is associative, i.e., (A ⊕ B) ⊕ C = A ⊕ (B ⊕ C).

a basic symmetric encryption algorithm.

P is the plaintext, and K is the secret key.

ciphertext is C = P ⊕ K.

C and K, we can recover P.

with C ⊕ K = (P ⊕ K) ⊕ K.

 (P ⊕ K) ⊕ K = P ⊕ (K ⊕ K)

K ⊕ K  = 0

P ⊕ 0 = P


## Modulo Operation


as % or as _m__o__d_.

_X_%_Y_, is the **remainder** when X is divided by Y.


```
a = q × n + r
```

where:

- `a` = dividend
- `n` = divisor
- `q` = quotient
- `r` = remainder (this is what `%` returns)


The remainder must always satisfy:

```
0 ≤ remainder < divisor
```