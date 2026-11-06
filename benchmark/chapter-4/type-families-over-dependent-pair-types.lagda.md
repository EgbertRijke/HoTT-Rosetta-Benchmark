# Type Families Over Dependent Pair Types

```agda
module chapter-4.type-families-over-dependent-pair-types where

open import universe-levels
open import chapter-4.dependent-pair-types
```

## Statement

Any binary family of types `C : (x : A) → B x → 𝒰` determines a family of types over `Σ A B`.

## Formalization

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : A → UU l2}
  where

  fam-Σ : ((x : A) → B x → UU l3) → Σ A B → UU l3
  fam-Σ C (x , y) = C x y
```
