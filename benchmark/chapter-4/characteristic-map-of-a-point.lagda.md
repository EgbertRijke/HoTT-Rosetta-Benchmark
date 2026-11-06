# The Characteristic Map of a Point

```agda
module chapter-4.characteristic-map-of-a-point where

open import universe-levels
open import chapter-4.unit-type
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
