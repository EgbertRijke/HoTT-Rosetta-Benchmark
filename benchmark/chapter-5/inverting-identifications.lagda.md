# Inverting Identifications

```agda
module chapter-5.inverting-identifications where

open import universe-levels
open import chapter-5.identity-types
```

## Statement

The inverse of an identification `p : x ＝ y` is an identification `inv p : y ＝ x`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  inv : {x y : A} → x ＝ y → y ＝ x
  inv refl = refl
```
