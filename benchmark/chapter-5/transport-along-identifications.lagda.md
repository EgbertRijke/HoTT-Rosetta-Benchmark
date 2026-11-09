# Transport Along Identifications

```agda
module chapter-5.transport-along-identifications where

open import universe-levels
open import chapter-5.identity-types
```

## Statement

An identification `p : x ＝ y` induces a transport function `B x → B y`, for every type family `B` over any type `A`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2) {x y : A}
  where

  tr : x ＝ y → B x → B y
  tr refl b = b
```
