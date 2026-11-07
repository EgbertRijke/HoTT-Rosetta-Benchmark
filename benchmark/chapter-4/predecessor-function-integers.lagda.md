# The Predecessor Function on the Integers

```agda
module chapter-4.predecessor-function-integers where

open import chapter-3
open import chapter-4.unit-type
open import chapter-4.coproduct-types
open import chapter-4.integers
```

## Statement

Define the predecessor function on the integers

## Formalization

```agda
pred-ℤ : ℤ → ℤ
pred-ℤ (inl x) = inl (succ-ℕ x)
pred-ℤ (inr (inl star)) = inl zero-ℕ
pred-ℤ (inr (inr zero-ℕ)) = inr (inl star)
pred-ℤ (inr (inr (succ-ℕ x))) = inr (inr x)
```
