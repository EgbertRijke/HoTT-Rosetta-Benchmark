# The Left Successor Law for Multiplication of Natural Numbers

```agda
module chapter-5.left-successor-law-multiplication-natural-numbers where

open import chapter-3
open import chapter-5.identity-types
```

## Statement

The left successor law for multiplication of natural numbers asserts that `(x + 1) * y ＝ x * y + y`. This law holds by judgmental equality.

## Formalization

```agda
left-successor-law-mul-ℕ :
  (x y : ℕ) → (succ-ℕ x) *ℕ y ＝ (x *ℕ y) +ℕ y
left-successor-law-mul-ℕ x y = refl
```
