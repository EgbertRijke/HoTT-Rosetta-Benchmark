# The Induction Principle of Cartesian Product Types

```agda
module chapter-4.induction-cartesian-product-types where

open import universe-levels
open import chapter-4.cartesian-product-types
open import chapter-4.dependent-pair-types
```

## Statement

The induction principle of cartesian product types asserts that for every type family `C : A × B → 𝒰` there is a function

```text
  ((x : A) (y : B) → C (x , y)) → (t : A × B) → C t.
```

## Formalization

```agda
ind-product :
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {C : A × B → UU l3} →
  ((x : A) (y : B) → C (x , y)) → (t : A × B) → C t
ind-product f (x , y) = f x y
```
