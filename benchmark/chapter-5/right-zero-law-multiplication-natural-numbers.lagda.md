# The Right Zero Law for Multiplication of Natural Numbers

```agda
module chapter-5.right-zero-law-multiplication-natural-numbers where

open import chapter-3
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.right-unit-law-addition-natural-numbers
```

## Statement

The right zero law for multiplication of natural numbers asserts that `x * 0 ＝ 0`.

## Formalization

```agda
right-zero-law-mul-ℕ :
  (x : ℕ) → x *ℕ zero-ℕ ＝ zero-ℕ
right-zero-law-mul-ℕ zero-ℕ =
  refl
right-zero-law-mul-ℕ (succ-ℕ x) =
  ( right-unit-law-add-ℕ (x *ℕ zero-ℕ)) ∙ (right-zero-law-mul-ℕ x)
```
