# The Action on Identifications of Dependent Functions

```agda
module chapter-5.action-on-identifications-dependent-functions where

open import universe-levels
open import chapter-5.dependent-identifications
open import chapter-5.identity-types
```

## Statement

Consider a dependent function `f : (x : A) → B x`. The action on identifications of `f` is a dependent function

```text
  {x y : A} (p : x ＝ y) → dependent-identification B p (f x) (f y).
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : A → UU l2} (f : (x : A) → B x)
  where

  apd :
    {x y : A} (p : x ＝ y) → dependent-identification B p (f x) (f y)
  apd refl = refl
```
