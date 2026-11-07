# The Negative Function on the Integers

```agda
module chapter-4.negative-function-integers where

open import chapter-4.coproduct-types
open import chapter-4.integers
open import chapter-4.unit-type
```

## Statement

Define the function `x ↦ -x` on the integers.

## Formalization

```agda
neg-ℤ : ℤ → ℤ
neg-ℤ (inl x) = inr (inr x)
neg-ℤ (inr (inl star)) = inr (inl star)
neg-ℤ (inr (inr x)) = inl x
```
