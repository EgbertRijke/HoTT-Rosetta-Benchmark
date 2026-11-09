# The Left Successor Law for Addition of Natural Numbers

```agda
module chapter-5.left-successor-law-addition-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

The left successor law for addition of natural numbers asserts that `succ-ℕ x + y ＝ succ-ℕ (x + y)`.

## Formalization

```agda
left-successor-law-add-ℕ :
  (x y : ℕ) → succ-ℕ x +ℕ y ＝ succ-ℕ (x +ℕ y)
left-successor-law-add-ℕ x zero-ℕ = refl
left-successor-law-add-ℕ x (succ-ℕ y) =
  ap succ-ℕ (left-successor-law-add-ℕ x y)
```
