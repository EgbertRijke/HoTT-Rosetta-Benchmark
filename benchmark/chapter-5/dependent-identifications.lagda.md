# Dependent Identifications

```agda
module chapter-5.dependent-identifications where

open import universe-levels
open import chapter-5.identity-types
open import chapter-5.transport-along-identifications
```

## Statement

Let `B` be a type family over `A`. The type of dependent identifications from `u : B x` to `v : B y` over an identification `p : x ＝ y` is defined to be the type

```text
  tr B p u ＝ v.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2)
  where

  dependent-identification :
    {x x' : A} (p : x ＝ x') → B x → B x' → UU l2
  dependent-identification p u v = (tr B p u ＝ v)
```
