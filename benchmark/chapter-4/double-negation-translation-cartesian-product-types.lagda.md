# Double Negation Translation of Cartesian Product Types

```agda
module chapter-4.double-negation-translation-cartesian-product-types where

open import universe-levels
open import chapter-4.binary-functoriality-double-negation
open import chapter-4.cartesian-product-types
open import chapter-4.dependent-pair-types
open import chapter-4.double-negation
open import chapter-4.logical-equivalences
```

## Statement

There is a logical equivalence between `¬¬ (A × B)` and `¬¬ A × ¬¬ B`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where

  forward-implication-double-negation-translation-product :
    ¬¬ (A × B) → ¬¬ A × ¬¬ B
  pr1 (forward-implication-double-negation-translation-product H) f =
    H (λ (a , b) → f a)
  pr2 (forward-implication-double-negation-translation-product H) g =
    H (λ (a , b) → g b)

  backward-implication-double-negation-translation-product :
    ¬¬ A × ¬¬ B → ¬¬ (A × B)
  backward-implication-double-negation-translation-product (a , b) =
    binary-map-double-negation _,_ a b

  double-negation-translation-product :
    ¬¬ (A × B) ↔ ¬¬ A × ¬¬ B
  pr1 double-negation-translation-product =
    forward-implication-double-negation-translation-product
  pr2 double-negation-translation-product =
    backward-implication-double-negation-translation-product
```
