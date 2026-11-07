# Irrefutability of Double Negation Elimination

```agda
module chapter-4.irrefutability-of-double-negation-elimination where

open import universe-levels
open import chapter-4.double-negation
open import chapter-4.ex-falso
open import chapter-4.negation
```

## Statement

Double negation elimination, which asserts that `¬¬ A → A`, is irrefutable in the sense that there is an element of type

```text
  ¬¬ (¬¬ A → A).
```

## Formalization

```agda
double-negation-double-negation-elim :
  {l : Level} {P : UU l} → ¬¬ (¬¬ P → P)
double-negation-double-negation-elim {P = P} f =
  ( λ (np : ¬ P) → f (λ (nnp : ¬¬ P) → ex-falso (nnp np)))
  ( λ (p : P) → f (λ (nnp : ¬¬ P) → p))
```
