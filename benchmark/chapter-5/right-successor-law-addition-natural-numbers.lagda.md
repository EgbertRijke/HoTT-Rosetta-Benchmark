# The Right Successor Law for Addition of Natural Numbers

```agda
module chapter-5.right-successor-law-addition-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

The right successor law for addition of natural numbers asserts that `x + succ-ℕ y ＝ succ-ℕ (x + y)`. This law holds by judmental equality.

## Formalization

```agda
right-successor-law-add-ℕ :
  (x y : ℕ) → x +ℕ (succ-ℕ y) ＝ succ-ℕ (x +ℕ y)
right-successor-law-add-ℕ x y = refl
```
