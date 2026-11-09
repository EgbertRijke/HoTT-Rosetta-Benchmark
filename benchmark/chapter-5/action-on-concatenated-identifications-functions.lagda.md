# The Action of Functions on Concatenated Identifications

```agda
module chapter-5.action-on-concatenated-identifications-functions where

open import universe-levels
open import chapter-5.action-on-identifications-functions
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

The action on identifications of a function `f : A → B` acts on a concatenated identifications `p ∙ q` as a concatenation:

```text
  ap f (p ∙ q) ＝ ap f p ∙ ap f q.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (f : A → B)
  where

  ap-concat :
    {x y z : A} (p : x ＝ y) (q : y ＝ z) → ap f (p ∙ q) ＝ ap f p ∙ ap f q
  ap-concat refl q = refl
```
