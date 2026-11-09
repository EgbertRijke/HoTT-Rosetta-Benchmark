# The Action on Identifications of Dependent Functions into Constant Type Families

```agda
module chapter-5.action-on-identifications-dependent-functions-constant-type-families where

open import universe-levels
open import chapter-1
open import chapter-5.action-on-identifications-dependent-functions
open import chapter-5.action-on-identifications-functions
open import chapter-5.concatenation-identifications
open import chapter-5.dependent-identifications
open import chapter-5.identity-types
open import chapter-5.transport-along-identifications-constant-type-family
```

## Statement

When we view a function `f : A → B` as a dependent function into the constant type family `B` over `A`, its action on identifications is computed by

```text
  apd f p ＝ tr-constant-type-family p (f x) ∙ ap f p.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (f : A → B)
  where

  apd-constant-type-family :
    {x y : A} (p : x ＝ y) → apd f p ＝ tr-constant-type-family p (f x) ∙ ap f p
  apd-constant-type-family refl = refl
```
