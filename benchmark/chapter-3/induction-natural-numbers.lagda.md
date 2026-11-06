# The Induction Principle for the Natural Numbers

```agda
module chapter-3.induction-natural-numbers where

open import universe-levels
open import chapter-3.natural-numbers
```

## Statement

The induction principle of `ℕ` can be stated as the following inference rule

```text
   Γ, n : ℕ ⊢ P(n) type
  ------------------------------------------------------------------
   Γ ⊢ ind-ℕ : P(0) → (Π(n : ℕ) P(n) → P(succ-ℕ(n))) → Π(n : ℕ) P(n).
```

## Formalization

```agda
ind-ℕ :
  {l : Level} {P : ℕ → UU l} →
  P 0 → ((n : ℕ) → P n → P (succ-ℕ n)) → ((n : ℕ) → P n)
ind-ℕ p-zero p-succ 0 = p-zero
ind-ℕ p-zero p-succ (succ-ℕ n) = p-succ n (ind-ℕ p-zero p-succ n)
```
