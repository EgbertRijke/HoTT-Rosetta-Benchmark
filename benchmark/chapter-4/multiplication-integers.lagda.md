# Multiplication of Integers

```agda
module chapter-4.multiplication-integers where

open import chapter-3
open import chapter-4.addition-integers
open import chapter-4.coproduct-types
open import chapter-4.integers
open import chapter-4.negative-function-integers
open import chapter-4.zero-integer
```

## Statement

Define multiplication on the integers.

## Formalization

```agda
infixl 40 _*ℤ_

_*ℤ_ : ℤ → ℤ → ℤ
inl zero-ℕ *ℤ l = neg-ℤ l
inl (succ-ℕ x) *ℤ l = (neg-ℤ l) +ℤ (inl x *ℤ l)
inr (inl _) *ℤ l = zero-ℤ
inr (inr zero-ℕ) *ℤ l = l
inr (inr (succ-ℕ x)) *ℤ l = l +ℤ (inr (inr x) *ℤ l)
```
