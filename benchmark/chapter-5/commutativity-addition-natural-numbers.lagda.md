# Commutativity of Addition of Natural Numbers

```agda
module chapter-5.commutativity-addition-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.left-successor-law-addition-natural-numbers
open import chapter-5.left-unit-law-addition-natural-numbers
```

## Statement

Addition of natural numbers is commutative, in the sense that `x + y ＝ y + x`.

## Formalization

```agda
commutative-add-ℕ :
  (x y : ℕ) → x +ℕ y ＝ y +ℕ x
commutative-add-ℕ zero-ℕ y =
  left-unit-law-add-ℕ y
commutative-add-ℕ (succ-ℕ x) y =
  left-successor-law-add-ℕ x y ∙ ap succ-ℕ (commutative-add-ℕ x y)
```
