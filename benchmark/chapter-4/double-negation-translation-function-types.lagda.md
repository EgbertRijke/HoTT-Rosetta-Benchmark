# Double Negation Translation of Cartesian Product Types

```agda
module chapter-4.double-negation-translation-function-types where

open import universe-levels
open import chapter-2
open import chapter-4.double-negation
open import chapter-4.double-negation-elimination-function-types
open import chapter-4.functoriality-double-negation
```

## Statement

There is a logical equivalence between `¬¬ (A → B)` and `¬¬ A → ¬¬ B`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where

  forward-implication-double-negation-translation-function-type :
    ¬¬ (A → B) → ¬¬ A → ¬¬ B
  forward-implication-double-negation-translation-function-type H =
    double-negation-elimination-function-type
      ( map-double-negation map-double-negation H)
```
