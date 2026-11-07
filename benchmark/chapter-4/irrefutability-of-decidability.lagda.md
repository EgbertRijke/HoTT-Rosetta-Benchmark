# Irrefutability of Decidability

```agda
module chapter-4.irrefutability-of-decidability where

open import universe-levels
open import chapter-2
open import chapter-4.coproduct-types
open import chapter-4.double-negation
open import chapter-4.negation
```

## Statement

Decidability of a type `A`, which asserts that `A + ¬ A`, is irrefutable in the sense that there is an element of type

```text
  ¬¬ (A + ¬ A).
```

## Formalization

```agda
is-irrefutable-is-decidable :
  {l : Level} {A : UU l} → ¬¬ (A + ¬ A)
is-irrefutable-is-decidable H = H (inr (H ∘ inl))
```
