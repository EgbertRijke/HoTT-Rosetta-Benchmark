# Exponentiation of Natural Numbers

```agda
module chapter-3.exponentiation where

open import chapter-3.natural-numbers
open import chapter-3.multiplication-natural-numbers
```

## Statement

Define the **exponentiation function** `n,m ↦ m^n` of type `ℕ → (ℕ → ℕ)`.

## Formalization

```agda
exp-ℕ : ℕ → ℕ → ℕ
exp-ℕ m zero-ℕ = 1
exp-ℕ m (succ-ℕ zero-ℕ) = m
exp-ℕ m (succ-ℕ (succ-ℕ n)) = exp-ℕ m (succ-ℕ n) *ℕ m
```

## Syntax

```agda
infixr 45 _^ℕ_
_^ℕ_ = exp-ℕ
```

