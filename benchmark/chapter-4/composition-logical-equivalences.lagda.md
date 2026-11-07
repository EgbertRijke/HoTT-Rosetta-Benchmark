# Composition of logical equivalences

```agda
module chapter-4.composition-logical-equivalences where

open import universe-levels
open import chapter-2
open import chapter-4.dependent-pair-types
open import chapter-4.logical-equivalences
```

## Statement

Any two logical equivalences `B ↔ C` and `A ↔ B` compose to a logical equivalence `A ↔ C`.

## Formalization

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {C : UU l3}
  where

  infixr 15 _∘iff_

  _∘iff_ : (B ↔ C) → (A ↔ B) → (A ↔ C)
  pr1 ((g1 , g2) ∘iff (f1 , f2)) = g1 ∘ f1
  pr2 ((g1 , g2) ∘iff (f1 , f2)) = f2 ∘ g2
```
