# The Right Unit Law for Multiplication of Natural Numbers

```agda
module chapter-5.right-unit-law-multiplication-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

The right unit law for multiplication of natural numbers asserts that `x * 1 ＝ x`. This law holds by judgmental equality.

## Formalization

```agda
right-unit-law-mul-ℕ :
  (x : ℕ) → x *ℕ 1 ＝ x
right-unit-law-mul-ℕ zero-ℕ = refl
right-unit-law-mul-ℕ (succ-ℕ x) = ap succ-ℕ (right-unit-law-mul-ℕ x)
```
