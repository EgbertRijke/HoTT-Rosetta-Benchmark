# Double Negation Elimination of Cartesian Products of Double Negation Stable Types

```agda
module chapter-4.double-negation-elimination-cartesian-product-types where

open import universe-levels
open import chapter-4.cartesian-product-types
open import chapter-4.dependent-pair-types
open import chapter-4.double-negation
```

## Statement

The type `¬¬ A × ¬¬ B` has double negation elimination.

## Formalization

```agda
double-negation-elimination-product :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  ¬¬ (¬¬ A × ¬¬ B) → ¬¬ A × ¬¬ B
pr1 (double-negation-elimination-product H) f = H (λ (a , b) → a f)
pr2 (double-negation-elimination-product H) g = H (λ (a , b) → b g)
```
