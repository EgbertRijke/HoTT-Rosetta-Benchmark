# The Integer Negative One

```agda
module chapter-4.negative-one-integer where

open import chapter-4.inclusion-of-negative-integers
open import chapter-4.integers
```

## Statement

The integer `-1` is defined to be `in-neg-ℤ 0`.

## Formalization

```agda
neg-one-ℤ : ℤ
neg-one-ℤ = in-neg-ℤ 0
```
