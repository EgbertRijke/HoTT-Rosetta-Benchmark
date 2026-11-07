# Double Negation Elimination of Function Types into Double Negation Stable Types

```agda
module chapter-4.double-negation-elimination-function-types where

open import universe-levels
open import chapter-4.double-negation
```

## Statement

The type `A → ¬¬ B` has double negation elimination.

## Formalization

```agda
double-negation-elimination-function-type :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  ¬¬ (A → ¬¬ B) → (A → ¬¬ B)
double-negation-elimination-function-type H a f =
  H (λ g → g a f)
```
