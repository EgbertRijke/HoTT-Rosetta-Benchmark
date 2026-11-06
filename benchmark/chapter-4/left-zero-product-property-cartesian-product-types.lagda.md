# Left Zero-Product Property Cartesian Product Types

```agda
module chapter-4.left-zero-product-property-cartesian-product-types where

open import universe-levels
open import chapter-4.cartesian-product-types
open import chapter-4.dependent-pair-types
open import chapter-4.empty-types
```

## Statement

If `A × B` is empty and an element of `B` is given, then `A` is empty.

## Formalization

```agda
is-empty-left-factor-is-empty-product :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} → is-empty (A × B) → B → is-empty A
is-empty-left-factor-is-empty-product f b a = f (a , b)
```
