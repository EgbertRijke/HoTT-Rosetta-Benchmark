# Irrefutable Implications

```agda
module chapter-4.irrefutable-implications where

open import universe-levels
open import chapter-4.coproduct-types
open import chapter-4.dependent-pair-types
open import chapter-4.double-negation
open import chapter-4.ex-falso
open import chapter-4.logical-equivalences
open import chapter-4.negation
```

## Statement

An implication `B → A` is irrefutable if and only if it is implied by the decidability of `A`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where

  forward-implication-irrefutable-implication :
    ¬¬ (B → A) → (A + ¬ A) → (B → A)
  forward-implication-irrefutable-implication H (inl a) b =
    a
  forward-implication-irrefutable-implication H (inr f) b =
    ex-falso (H (λ g → f (g b)))

  backward-implication-irrefutable-implication :
    ((A + ¬ A) → (B → A)) → ¬¬ (B → A)
  backward-implication-irrefutable-implication f g =
    g (f (inr (λ a → g (λ _ → a))))

  logical-equivalence-irrefutable-implication :
    ¬¬ (B → A) ↔ ((A + ¬ A) → (B → A))
  pr1 logical-equivalence-irrefutable-implication =
    forward-implication-irrefutable-implication
  pr2 logical-equivalence-irrefutable-implication =
    backward-implication-irrefutable-implication
```

## Remark

In the formalization below we see an important organizational principle that is upheld in agda-unimath: When an entry consists of several components, it is beneficial to split each component into its own entry.
