# The Action of Functions on Identifications of Identifications

```agda
module chapter-5.action-on-identifications-of-identifications-functions where

open import universe-levels
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

The action of a function `f : A → B` on an identification of identifications `α : p ＝ q` is the identification

```text
  ap² f = ap (ap f) α.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} {x y : A}
  {p q : x ＝ y} (f : A → B) (α : p ＝ q)
  where

  ap² : ap f p ＝ ap f q
  ap² = ap (ap f) α
```
