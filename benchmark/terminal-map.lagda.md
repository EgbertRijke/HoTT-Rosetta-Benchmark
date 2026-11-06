# The terminal map

```agda
module terminal-map where

open import universe-levels
open import definition-4-2-1-unit-type
open import exercise-2-3-constant-maps
```

## Statement

The terminal map out of a type `A` is the map `A → unit` given by `a ↦ star`.

## Formalization

```agda
module _
  {l : Level} (A : UU l)
  where

  terminal-map : A → unit
  terminal-map = const A star
```
