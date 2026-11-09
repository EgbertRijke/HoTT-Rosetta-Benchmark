# Associativity of Addition of Natural Numbers

```agda
module chapter-5.associativity-addition-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

Addition of natural numbers is associative, in the sense that `(x + y) + z ＝ x + (y + z)`.

## Formalization

```agda
associative-add-ℕ :
  (x y z : ℕ) → (x +ℕ y) +ℕ z ＝ x +ℕ (y +ℕ z)
associative-add-ℕ x y zero-ℕ = refl
associative-add-ℕ x y (succ-ℕ z) = ap succ-ℕ (associative-add-ℕ x y z)
```
