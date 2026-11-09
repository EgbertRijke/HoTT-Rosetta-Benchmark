# The Transport Along an Action on Identifications of a Function

```agda
module chapter-5.transport-along-action-on-identifications-functions where

open import universe-levels
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
open import chapter-5.transport-along-identifications
```

## Statement

Consider a type family `B : A → UU l2` and a type family `D : C → UU l4`, and consider functions

```text
  f : A → C,
  g : (x : A) → B x → D (f x).
```

Furthermore, consider an identification `p : x ＝ y` in `A` and an element `u : B x`. Then the transport of `g x u` along `ap f p` is `g y (tr B p u)`. That is, the square

```text
               tr B p
     B x -------------------> B y
      |                        |
  g x |                        | g y
      |                        |
      ∨                        ∨
   D (f x) ---------------> D (f y)
            tr D (ap f p)
```

commutes.

## Formalization

```agda
module _
  {l1 l2 l3 l4 : Level} {A : UU l1} {B : A → UU l2} {C : UU l3} {D : C → UU l4}
  (f : A → C) (g : (x : A) → B x → D (f x))
  where
  
  tr-ap :
    {x y : A} (p : x ＝ y) (u : B x) → tr D (ap f p) (g x u) ＝ g y (tr B p u)
  tr-ap refl z = refl
```
