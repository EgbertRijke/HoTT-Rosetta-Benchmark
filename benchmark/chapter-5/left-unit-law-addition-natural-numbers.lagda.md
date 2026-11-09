# The Left Unit Law for Addition of Natural Numbers

```agda
module chapter-5.left-unit-law-addition-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

The left unit law for addition of natural numbers asserts that `0 + x ＝ x`.

## Formalization

```agda
left-unit-law-add-ℕ :
  (x : ℕ) → zero-ℕ +ℕ x ＝ x
left-unit-law-add-ℕ zero-ℕ = refl
left-unit-law-add-ℕ (succ-ℕ x) = ap succ-ℕ (left-unit-law-add-ℕ x)
```
