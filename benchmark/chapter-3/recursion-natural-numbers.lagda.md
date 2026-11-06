# The Recursion Principle for the Natural Numbers

```agda
module chapter-3.recursion-natural-numbers where

open import universe-levels
open import chapter-3.natural-numbers
open import chapter-3.induction-natural-numbers
```

## Statement

The recursion principle of `ℕ` can be stated as the following inference rule

```text
   Γ, ⊢ A type
  ------------------------------------------------------------------
   Γ ⊢ rec-ℕ : A → (ℕ → A → A) → (ℕ → A).
```

## Formalization

```agda
rec-ℕ : {l : Level} {A : UU l} → A → (ℕ → A → A) → (ℕ → A)
rec-ℕ = ind-ℕ
```
