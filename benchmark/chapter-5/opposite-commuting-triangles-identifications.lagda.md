# Opposite Commuting Triangles of Identifications

```agda
module chapter-5.opposite-commuting-triangles-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

Consider identifications `p : x ＝ z`, `q : x ＝ y`, and `r : y ＝ z`. The type of coherences filling a commuting triangle of identifications

```text
       q
  x ------> y
   \       /
  p \     / r
     \   /
      ∨ ∨
       z
```

is the type `q ∙ r ＝ p`.

## Formalization

```agda
module _
  {l : Level} {A : UU l} {x y z : A}
  where

  coherence-triangle-identifications' :
    (left : x ＝ z) (right : y ＝ z) (top : x ＝ y) → UU l
  coherence-triangle-identifications' left right top = (top ∙ right ＝ left)
```
