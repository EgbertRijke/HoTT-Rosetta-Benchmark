# The Binary Maximum of Natural Numbers

```agda
module chapter-3.maximum-natural-numbers where

open import chapter-3.natural-numbers
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

