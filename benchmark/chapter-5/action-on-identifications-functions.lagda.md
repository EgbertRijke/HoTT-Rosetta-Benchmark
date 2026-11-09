# Action on Identifications of Functions

```agda
module chapter-5.action-on-identifications-functions where

open import universe-levels
open import chapter-5.identity-types
```

## Statement

Let `f : A → B` be a map. The **action on identifications** of `f` is a family of maps

```text
  ap_f : x = y → f(x) = f(y)
```

indexed by `x y : A`, defined by `ap_f refl ≔ refl`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (f : A → B)
  where

  ap : {x y : A} → x ＝ y → f x ＝ f y
  ap refl = refl
```
