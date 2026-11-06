# Diagonal Maps

```agda
module diagonal-maps where

open import universe-levels
open import exercise-2-3-constant-maps
```

## Statement

Construct the diagonal map of the exponential `A → (X → A)`

## Formalization

```agda
module _
  {l1 l2 : Level} (A : UU l1) (X : UU l2)
  where

  diagonal-exponential : A → X → A
  diagonal-exponential = const X
```
