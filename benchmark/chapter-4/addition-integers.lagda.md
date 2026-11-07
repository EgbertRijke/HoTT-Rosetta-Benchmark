# Addition on the Integers

```agda
module chapter-4.addition-integers where

open import chapter-3
open import chapter-4.coproduct-types
open import chapter-4.integers
open import chapter-4.predecessor-function-integers
open import chapter-4.successor-function-integers
```

## Statement

Define the addition operation on the integers.

## Formalization

```agda
infixl 35 _+ℤ_

_+ℤ_ : ℤ → ℤ → ℤ
inl zero-ℕ +ℤ l = pred-ℤ l
inl (succ-ℕ x) +ℤ l = pred-ℤ (inl x +ℤ l)
inr (inl _) +ℤ l = l
inr (inr zero-ℕ) +ℤ l = succ-ℤ l
inr (inr (succ-ℕ x)) +ℤ l = succ-ℤ (inr (inr x) +ℤ l)
```
