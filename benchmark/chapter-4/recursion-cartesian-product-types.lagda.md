# The Recursion Principle of Cartesian Product Types

```agda
module chapter-4.recursion-cartesian-product-types where

open import universe-levels
open import chapter-4.cartesian-product-types
open import chapter-4.dependent-pair-types
```

## Statement

The recursion principle of cartesian product types asserts that for every type family `C` there is a function

```text
  (A → B → C) → A × B → C.
```

## Formalization

```agda
rec-product :
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {C : UU l3} →
  (A → B → C) → A × B → C
rec-product f (x , y) = f x y
```
