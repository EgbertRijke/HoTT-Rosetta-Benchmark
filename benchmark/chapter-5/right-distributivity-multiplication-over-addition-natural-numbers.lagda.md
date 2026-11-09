# Right Distributivity of Multiplication over Addition of the Natural Numbers

```agda
module chapter-5.right-distributivity-multiplication-over-addition-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.commutativity-multiplication-natural-numbers
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.left-distributivity-multiplication-over-addition-natural-numbers
```

## Statement

Multiplication of natural numbers distributes from the right over addition, in the sense that `(x + y) * z ＝ x * z + y * z`. 

## Formalization

```agda
right-distributive-mul-add-ℕ :
  (x y z : ℕ) → (x +ℕ y) *ℕ z ＝ (x *ℕ z) +ℕ (y *ℕ z)
right-distributive-mul-add-ℕ x y z =
  ( commutative-mul-ℕ (x +ℕ y) z) ∙
  ( ( left-distributive-mul-add-ℕ z x y) ∙
    ( ( ap (_+ℕ (z *ℕ y)) (commutative-mul-ℕ z x)) ∙
      ( ap ((x *ℕ z) +ℕ_) (commutative-mul-ℕ z y))))
```
