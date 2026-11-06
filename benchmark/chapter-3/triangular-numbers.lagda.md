# The Triangular Numbers

```agda
module chapter-3.triangular-numbers where

open import chapter-3.natural-numbers
open import chapter-3.addition-natural-numbers
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
