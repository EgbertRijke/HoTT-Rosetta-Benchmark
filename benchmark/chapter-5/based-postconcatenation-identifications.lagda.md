# Based Postconcatenation of Identifications

```agda
module chapter-5.based-postconcatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

Consider a type `A` equipped with an element `x : A` and an identification `q : y ＝ z`. The **based postconcatenation operation** is a function of type

```text
  (x ＝ y) → (x ＝ z).
```

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  concat' : (x : A) {y z : A} → y ＝ z → x ＝ y → x ＝ z
  concat' x q p = p ∙ q
```
