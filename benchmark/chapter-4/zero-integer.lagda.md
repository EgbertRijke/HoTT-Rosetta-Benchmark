# The Integer Zero

```agda
module chapter-4.zero-integer where

open import chapter-4.coproduct-types
open import chapter-4.integers
open import chapter-4.unit-type
```

## Statement

The integer `0` is defined as `inr (inl star)`.

## Formalization

```agda
zero-ℤ : ℤ
zero-ℤ = inr (inl star)
```
