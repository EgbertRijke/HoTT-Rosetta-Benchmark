# The Right Unit Law for Addition of Natural Numbers

```agda
module chapter-5.right-unit-law-addition-natural-numbers where

open import chapter-3
open import chapter-5.identity-types
```

## Statement

The right unit law for addition of natural numbers asserts that `x + 0 ＝ x`.

## Formalization

```agda
right-unit-law-add-ℕ :
  (x : ℕ) → x +ℕ 0 ＝ x
right-unit-law-add-ℕ x = refl
```
