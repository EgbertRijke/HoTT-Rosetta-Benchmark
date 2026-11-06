# The Binary Minimum of Natural Numbers

```agda
module exercise-3-2-minimum-natural-numbers where

open import section-3-1-natural-numbers
```

## Statement

Define the binary **min** function

```text
    min-ℕ : ℕ → (ℕ → ℕ).
```

## Formalization

```agda
min-ℕ : ℕ → (ℕ → ℕ)
min-ℕ 0 n = 0
min-ℕ (succ-ℕ m) 0 = 0
min-ℕ (succ-ℕ m) (succ-ℕ n) = succ-ℕ (min-ℕ m n)
```

