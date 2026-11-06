# The Characteristic Map of a Point

```agda
module section-4-2-characteristic-map-of-a-point where

open import universe-levels
open import definition-4-2-1-unit-type
```

## Statement

The characteristic map of a point is the map

```text
  point : A → (𝟙 → A).
```

given by `point a x ≔ a`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  point : A → (unit → A)
  point a x = a
```
