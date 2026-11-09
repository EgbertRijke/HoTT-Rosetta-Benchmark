# The Action on Identifications of Addition on the Natural Numbers

```agda
module chapter-5.action-on-identifications-addition-natural-numbers where

open import chapter-3
open import chapter-5.action-on-identifications-binary-functions
open import chapter-5.identity-types
```

## Statement

Since every binary operation has an action on identifications, so does addition on the natural numbers.

## Formalization

```agda
ap-add-ℕ :
  {m n m' n' : ℕ} → m ＝ m' → n ＝ n' → m +ℕ n ＝ m' +ℕ n'
ap-add-ℕ p q = ap-binary _+ℕ_ p q
```
