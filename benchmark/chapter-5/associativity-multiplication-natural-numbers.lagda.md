# Associativity of Multiplication of Natural Numbers

```agda
module chapter-5.associativity-multiplication-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.right-distributivity-multiplication-over-addition-natural-numbers
```

## Statement

Multiplication of natural numbers is associative in the sense that `(x * y) * z ＝ x * (y * z)`.

## Formalization

```agda
associative-mul-ℕ :
  (x y z : ℕ) → (x *ℕ y) *ℕ z ＝ x *ℕ (y *ℕ z)
associative-mul-ℕ zero-ℕ y z = refl
associative-mul-ℕ (succ-ℕ x) y z =
  ( right-distributive-mul-add-ℕ (x *ℕ y) y z) ∙
  ( ap (_+ℕ (y *ℕ z)) (associative-mul-ℕ x y z))
```
