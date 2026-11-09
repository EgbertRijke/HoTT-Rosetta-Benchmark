# Inverse Transport Along Identifications

```agda
module chapter-5.inverse-transport-along-identifications where

open import universe-levels
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.transport-along-identifications
```

## Statement

An identification `p : x ＝ y` induces an inverse transport function `B y → B x`, for every type family `B` over any type `A`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2) {x y : A}
  where

  inv-tr : y ＝ x → B x → B y
  inv-tr p = tr B (inv p)
```
