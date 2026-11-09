# Left Distributivity of Multiplication over Addition of the Natural Numbers

```agda
module chapter-5.left-distributivity-multiplication-over-addition-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.associativity-addition-natural-numbers
open import chapter-5.commutativity-addition-natural-numbers
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.left-successor-law-multiplication-natural-numbers
```

## Statement

Multiplication of natural numbers distributes from the left over addition, in the sense that `x * (y + z) ＝ x * y + x * z`. 

## Formalization

```agda
left-distributive-mul-add-ℕ :
  (x y z : ℕ) → x *ℕ (y +ℕ z) ＝ (x *ℕ y) +ℕ (x *ℕ z)
left-distributive-mul-add-ℕ zero-ℕ y z = refl
left-distributive-mul-add-ℕ (succ-ℕ x) y z =
  ( left-successor-law-mul-ℕ x (y +ℕ z)) ∙
  ( ( ap (_+ℕ (y +ℕ z)) (left-distributive-mul-add-ℕ x y z)) ∙
    ( ( associative-add-ℕ (x *ℕ y) (x *ℕ z) (y +ℕ z)) ∙
      ( ( ap
          ( ( x *ℕ y) +ℕ_)
          ( ( inv (associative-add-ℕ (x *ℕ z) y z)) ∙
            ( ( ap (_+ℕ z) (commutative-add-ℕ (x *ℕ z) y)) ∙
              ( associative-add-ℕ y (x *ℕ z) z)))) ∙
        ( inv (associative-add-ℕ (x *ℕ y) y ((x *ℕ z) +ℕ z))))))
```
