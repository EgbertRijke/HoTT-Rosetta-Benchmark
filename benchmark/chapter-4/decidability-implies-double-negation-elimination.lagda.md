# Decidability Implies Double Negation Elimination

```agda
module chapter-4.decidability-implies-double-negation-elimination where

open import universe-levels
open import chapter-4.coproduct-types
open import chapter-4.double-negation
open import chapter-4.ex-falso
open import chapter-4.negation
```

## Statement

If a type `A` is decidable in the sense that it comes equipped with an element of type `A + ¬ A`, then it has double negation elimination.

## Formalization

```agda
double-negation-elim-is-decidable :
  {l : Level} {A : UU l} → A + ¬ A → (¬¬ A → A)
double-negation-elim-is-decidable (inl a) h = a
double-negation-elim-is-decidable (inr f) h = ex-falso (h f)
```
