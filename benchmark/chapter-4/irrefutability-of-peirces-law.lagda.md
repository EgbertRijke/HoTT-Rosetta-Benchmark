# Irrefutability of Peirce's Law

```agda
module chapter-4.irrefutability-of-peirces-law where

open import universe-levels
open import chapter-4.double-negation
open import chapter-4.ex-falso
open import chapter-4.negation
```

## Statement

Peirce's law, which asserts that there is a function ((A → B) → A) → A, is irrefutable in the sense that

```text
  ¬¬ ((A → B) → A) → A.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where

  double-negation-peirces-law :
    ¬¬ (((A → B) → A) → A)
  double-negation-peirces-law f =
    ( λ (na : ¬ A) → f (λ h → h (λ a → ex-falso (na a))))
    ( λ (a : A) → f (λ _ → a))
```
