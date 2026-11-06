# Factorials

```agda
module chapter-3.factorials where

open import chapter-3.natural-numbers
open import chapter-3.multiplication-natural-numbers
```

## Statement

Define the **factorial** operation `n ↦ n!`.

## Formalization

```agda
factorial-ℕ : ℕ → ℕ
factorial-ℕ 0 = 1
factorial-ℕ (succ-ℕ m) = factorial-ℕ m *ℕ succ-ℕ m
```
