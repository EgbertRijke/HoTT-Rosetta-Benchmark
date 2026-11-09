# Lifting Identifications to Dependent Pair Types

```agda
module chapter-5.lifting-identifications-dependent-pair-types where

open import universe-levels
open import chapter-4
open import chapter-5.identity-types
open import chapter-5.transport-along-identifications
```

## Statement

Let `B` be a type family over `A`, and consider an identification `p : a = x` in
`A`. For any `b : B(a)`, there is an identification

```text
  lift_B(p,b) : (a, b) = (x, tr_B(p, b)).
```

In other words, an identification `p : x = y` in the base type `A` lifts to
an identification in `Σ(x : A) B(x)` for every element in `B(x)`, analogous to
the path lifting property for fibrations in homotopy theory.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : A → UU l2}
  where

  lift-eq-Σ :
    {x y : A} (p : x ＝ y) (b : B x) → (x , b) ＝ (y , tr B p b)
  lift-eq-Σ refl b = refl
```
