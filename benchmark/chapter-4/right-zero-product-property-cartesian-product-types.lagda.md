# Right Zero-Product Property Cartesian Product Types

```agda
module chapter-4.right-zero-product-property-cartesian-product-types where

open import universe-levels
open import chapter-4.cartesian-product-types
open import chapter-4.dependent-pair-types
open import chapter-4.empty-types
```

## Statement

If `A × B` is empty and an element of `A` is given, then `B` is empty.

## Formalization

```agda
is-empty-right-factor-is-empty-product :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} → is-empty (A × B) → A → is-empty B
is-empty-right-factor-is-empty-product f a b = f (a , b)
```
