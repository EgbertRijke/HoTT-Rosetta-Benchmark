# Factorials

```agda
module exercise-3-3-factorials where

open import section-3-1-natural-numbers
open import exercise-3-1-multiplication-natural-numbers
```

## Statement

Define the **factorial** operation `n ↦ n!`.

## Formalization

```agda
factorial-ℕ : ℕ → ℕ
factorial-ℕ 0 = 1
factorial-ℕ (succ-ℕ m) = factorial-ℕ m *ℕ succ-ℕ m
```
