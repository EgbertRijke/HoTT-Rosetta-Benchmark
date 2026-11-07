# Inverse Logical Equivalences

```agda
module chapter-4.inverse-logical-equivalences where

open import universe-levels
open import chapter-4.dependent-pair-types
open import chapter-4.logical-equivalences
```

## Statement

The inverse of a logical equivalence `A ↔ B` is a logical equivalence `B ↔ A`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where

  inv-iff : (A ↔ B) → (B ↔ A)
  pr1 (inv-iff (f , g)) = g
  pr2 (inv-iff (f , g)) = f
```
