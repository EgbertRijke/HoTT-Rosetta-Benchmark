# The Raised Unit Type

```agda
module chapter-4.raised-unit-type where

open import universe-levels
open import chapter-2.constant-maps
open import chapter-4.unit-type
```

## Statement

The unit type raised to a universe `UU l` is a type in `UU l` defined using the `raise` operation. Its element is called `raise-star`.

## Formalization

```agda
raise-unit : (l : Level) → UU l
raise-unit l = raise l unit

raise-star : {l : Level} → raise l unit
raise-star = map-raise star
```
