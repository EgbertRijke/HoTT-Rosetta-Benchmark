# The Action on Identifications of Composite Functions

```agda
module chapter-5.action-on-identifications-composite-functions where

open import universe-levels
open import chapter-2
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

Consider two functions `g : B → C` and `f : A → B`. Then the action on identifications of the composite function `g ∘ f` is the composite of the action on identifications, in the sense that

```text
  ap (g ∘ f) p ＝ ap g (ap f p).
```

## Formalization

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {C : UU l3} (g : B → C) (f : A → B)
  where

  ap-comp : {x y : A} (p : x ＝ y) → ap (g ∘ f) p ＝ (ap g ∘ ap f) p
  ap-comp refl = refl
```
