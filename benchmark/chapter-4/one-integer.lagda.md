# The Integer One

```agda
module chapter-4.one-integer where

open import chapter-4.inclusion-of-positive-integers
open import chapter-4.integers
```

## Statement

The integer `1` is defined as `in-pos-ℤ 0`.

## Formalization

```agda
one-ℤ : ℤ
one-ℤ = in-pos-ℤ 0
```
