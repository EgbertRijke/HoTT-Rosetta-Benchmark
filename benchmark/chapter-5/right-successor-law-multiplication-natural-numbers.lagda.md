# The Right Successor Law for Multiplication of Natural Numbers

```agda
module chapter-5.right-successor-law-multiplication-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.associativity-addition-natural-numbers
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.left-successor-law-addition-natural-numbers
```

## Statement

The right successor law for multiplication of natural numbers asserts that `(x + 1) * y ＝ x * y + y`. This law holds by judgmental equality.

## Formalization

```agda
right-successor-law-mul-ℕ :
  (x y : ℕ) → x *ℕ (succ-ℕ y) ＝ x +ℕ (x *ℕ y)
right-successor-law-mul-ℕ zero-ℕ y = refl
right-successor-law-mul-ℕ (succ-ℕ x) y =
  ( ( ap (λ t → succ-ℕ (t +ℕ y)) (right-successor-law-mul-ℕ x y)) ∙
    ( ap succ-ℕ (associative-add-ℕ x (x *ℕ y) y))) ∙
  ( inv (left-successor-law-add-ℕ x ((x *ℕ y) +ℕ y)))

```
