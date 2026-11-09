# Transposing Transport Along Inverse Identifications

```agda
module chapter-5.transposing-transport-along-inverse-identifications where

open import universe-levels
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.transport-along-identifications
```

## Statement

Consider an identification `p : x ＝ y` and two elements `u : B x` and `v : B y` in the fibers of a type family `B` over `A`. Then there are transposition functions

```text
  v ＝ tr B p u → tr B (inv p) v ＝ u
```

and

```text
  tr B p u ＝ v → u ＝ tr B (inv p) v.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : A → UU l2}
  where

  eq-transpose-tr :
    {x y : A} (p : x ＝ y) {u : B x} {v : B y} →
    v ＝ tr B p u → tr B (inv p) v ＝ u
  eq-transpose-tr refl q = q

  eq-transpose-tr' :
    {x y : A} (p : x ＝ y) {u : B x} {v : B y} →
    tr B p u ＝ v → u ＝ tr B (inv p) v
  eq-transpose-tr' refl q = q
```
