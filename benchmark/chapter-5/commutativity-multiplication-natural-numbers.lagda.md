# Commutativity of Multiplication of Natural Numbers

```agda
module chapter-5.commutativity-multiplication-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.commutativity-addition-natural-numbers
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.right-successor-law-multiplication-natural-numbers
open import chapter-5.right-zero-law-multiplication-natural-numbers
```

## Statement

Multiplication of natural numbers is commutative in the sense that `x * y ＝ y * x`.

## Formalization

```agda
commutative-mul-ℕ :
  (x y : ℕ) → x *ℕ y ＝ y *ℕ x
commutative-mul-ℕ zero-ℕ y = inv (right-zero-law-mul-ℕ y)
commutative-mul-ℕ (succ-ℕ x) y =
  ( commutative-add-ℕ (x *ℕ y) y) ∙
  ( ( ap (y +ℕ_) (commutative-mul-ℕ x y)) ∙
    ( inv (right-successor-law-mul-ℕ y x)))
```
