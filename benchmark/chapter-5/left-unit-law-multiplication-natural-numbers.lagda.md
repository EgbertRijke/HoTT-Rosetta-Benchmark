# The Left Unit Law for Multiplication of Natural Numbers

```agda
module chapter-5.left-unit-law-multiplication-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

The left unit law for multiplication of natural numbers asserts that `1 * x ＝ x`.

## Formalization

```agda
left-unit-law-mul-ℕ :
  (x : ℕ) → 1 *ℕ x ＝ x
left-unit-law-mul-ℕ zero-ℕ = refl
left-unit-law-mul-ℕ (succ-ℕ x) = ap succ-ℕ (left-unit-law-mul-ℕ x)
```
