# Transport in the Constant Type Family Along Identifications

```agda
module chapter-5.transport-along-identifications-constant-type-family where

open import universe-levels
open import chapter-1
open import chapter-5.dependent-identifications
open import chapter-5.identity-types
```

## Statement

Transport in the constant type family `B` over `A` is the identity function.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where

  tr-constant-type-family :
    {x y : A} (p : x ＝ y) (b : B) →
    dependent-identification (constant-type-family A B) p b b
  tr-constant-type-family refl b = refl
```
