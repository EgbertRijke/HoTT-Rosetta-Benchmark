# The Binary Maximum of Natural Numbers

```agda
module exercise-3-2-maximum-natural-numbers where

open import section-3-1-natural-numbers
```

## Statement

Define the binary **max** function

```text
    max-ℕ : ℕ → (ℕ → ℕ).
```

## Formalization

```agda
max-ℕ : ℕ → (ℕ → ℕ)
max-ℕ 0 n = 0
max-ℕ (succ-ℕ m) 0 = 0
max-ℕ (succ-ℕ m) (succ-ℕ n) = succ-ℕ (max-ℕ m n)
```

