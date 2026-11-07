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
is-irrefutable-double-negation-elim :
  {l : Level} {A : UU l} → ¬¬ (¬¬ A → A)
is-irrefutable-double-negation-elim {A = A} f =
  ( λ (na : ¬ A) → f (λ (nna : ¬¬ A) → ex-falso (nna na)))
  ( λ (a : A) → f (λ (nna : ¬¬ A) → a))
```
