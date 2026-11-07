# Double Negation Elimination Negated Types

```agda
module chapter-4.double-negation-elimination-negated-types where

open import universe-levels
open import chapter-2
open import chapter-4.triple-negation
open import chapter-4.negation
```

## Statement

Negated types satisfy double negation elimination.

## Formalization

```agda
double-negation-elim-neg :
  {l : Level} (A : UU l) → ¬¬¬ A → ¬ A
double-negation-elim-neg A f p = f (ev p)
```
