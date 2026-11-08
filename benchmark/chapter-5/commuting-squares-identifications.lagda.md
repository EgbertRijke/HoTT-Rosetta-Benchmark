# Commuting Squares of Identifications

```agda
module chapter-5.commuting-squares-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

Consider identifications `top : x ＝ y`, `left : x ＝ z`, `right : y ＝ w`, and `bottom : z ＝ w`, as indicated in the square

```text
           top
       x ------> y
       |         |
  left |         | right
       |         |
       ∨         ∨
       z ------> w.
         bottom
```

The type of coherences witnessing that this square commuts is the type `left ∙ bottom ＝ top ∙ right`.

## Formalization

```agda
module _
  {l : Level} {A : UU l} {x y z w : A}
  (top : x ＝ y) (left : x ＝ z) (right : y ＝ w) (bottom : z ＝ w)
  where

  coherence-square-identifications : UU l
  coherence-square-identifications = left ∙ bottom ＝ top ∙ right
```
