# The Action of Functions on Inverted Identifications

```agda
module chapter-5.action-on-inverted-identifications-functions where

open import universe-levels
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
```

## Statement

The action on identifications of a function `f : A → B` acts on an inverted identification `inv p` as an inverse:

```text
  ap f (inv p) ＝ inv (ap f p).
```


## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (f : A → B) {x y : A}
  where

  ap-inv : (p : x ＝ y) → ap f (inv p) ＝ inv (ap f p)
  ap-inv refl = refl
```
