# The terminal map

```agda
module chapter-4.terminal-map where

open import universe-levels
open import chapter-4.unit-type
open import chapter-2.constant-maps
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
