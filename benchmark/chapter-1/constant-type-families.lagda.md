# Constant Type Families

```agda
module chapter-1.constant-type-families where

open import universe-levels
```

## Statement

The constant type family `B` over `A`, or weakening of `B` to `A`, is the type family `A → UU l2` given by `a ↦ B`.

## Formalization

```agda
module _
  {l1 l2 : Level} (A : UU l1) (B : UU l2)
  where

  constant-type-family : A → UU l2
  constant-type-family a = B
```
