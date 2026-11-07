# Double Negation Translation of Cartesian Product Types

```agda
module chapter-4.double-negation-translation-coproduct-types where

open import universe-levels
open import chapter-4.cartesian-product-types
open import chapter-4.coproduct-types
open import chapter-4.dependent-pair-types
open import chapter-4.double-negation
open import chapter-4.functoriality-negation
open import chapter-4.logical-equivalences
open import chapter-4.negation
```

## Statement

There is a logical equivalence between `¬¬ (A + B)` and `¬ (¬ A × ¬ B)`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where

  forward-implication-double-negation-translation-coproduct :
    ¬¬ (A + B) → ¬ (¬ A × ¬ B)
  forward-implication-double-negation-translation-coproduct H (f , g) =
    H (λ { (inl a) → f a ; (inr b) → g b})

  backward-implication-double-negation-translation-coproduct :
    ¬ (¬ A × ¬ B) → ¬¬ (A + B)
  backward-implication-double-negation-translation-coproduct H f =
    H (map-neg inl f , map-neg inr f)

  double-negation-translation-coproduct :
    ¬¬ (A + B) ↔ ¬ (¬ A × ¬ B)
  pr1 double-negation-translation-coproduct =
    forward-implication-double-negation-translation-coproduct
  pr2 double-negation-translation-coproduct =
    backward-implication-double-negation-translation-coproduct
```
