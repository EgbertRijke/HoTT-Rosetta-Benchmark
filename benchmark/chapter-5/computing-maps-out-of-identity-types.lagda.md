# Computing Maps Out of Identity Types

```agda
module chapter-5.computing-maps-out-of-identity-types where

open import universe-levels
open import chapter-5.identity-types
open import chapter-5.transport-along-identifications
```

## Statement

Every family of maps `f : (x : A) → a ＝ x → B x` is computed by transporting `f a refl`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : A → UU l2} {a : A}
  (f : (x : A) → a ＝ x → B x)
  where

  compute-map-out-of-identity-type :
    (x : A) (p : a ＝ x) → f x p ＝ tr B p (f a refl)
  compute-map-out-of-identity-type x refl = refl
```
