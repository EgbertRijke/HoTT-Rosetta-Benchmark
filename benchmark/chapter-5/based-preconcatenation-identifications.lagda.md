# Based Preconcatenation of Identifications

```agda
module chapter-5.based-preconcatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

Consider a type `A` equipped with an identification `p : x ＝ y` and an element `z : A`. The **based preconcatenation operation** is a function of type

```text
  (y ＝ z) → (x ＝ z).
```

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  concat : {x y : A} → x ＝ y → (z : A) → y ＝ z → x ＝ z
  concat p z q = p ∙ q
```
