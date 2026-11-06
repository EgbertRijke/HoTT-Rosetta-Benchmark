# The Triangular Numbers

```agda
module exercise-3-3-triangular-numbers where

open import section-3-1-natural-numbers
open import section-3-2-addition-natural-numbers
```

## Statement

Define the **triangular numbers**

```text
  1 + ⋯ + n.
```

## Formalization

```agda
triangular-number-ℕ : ℕ → ℕ
triangular-number-ℕ 0 = 0
triangular-number-ℕ (succ-ℕ n) = triangular-number-ℕ n +ℕ succ-ℕ n
```
