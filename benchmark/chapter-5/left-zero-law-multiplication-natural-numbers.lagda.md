# The Left Zero Law for Multiplication of Natural Numbers

```agda
module chapter-5.left-zero-law-multiplication-natural-numbers where

open import chapter-3
open import chapter-5.identity-types
```

## Statement

The left zero law for multiplication of natural numbers asserts that `0 * x ＝ 0`. This law holds by judgmental equality.

## Formalization

```agda
left-zero-law-mul-ℕ : (x : ℕ) → 0 *ℕ x ＝ 0
left-zero-law-mul-ℕ x = refl
```
