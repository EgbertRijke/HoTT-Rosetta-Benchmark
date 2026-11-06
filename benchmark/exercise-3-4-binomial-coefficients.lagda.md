# The Binomial Coefficients

```agda
module exercise-3-4-binomial-coefficients where

open import section-3-1-natural-numbers
open import section-3-2-addition-natural-numbers
```

## Statement

Define the **binomial coefficient**  `(n choose k)` for any `n k : ℕ`, making sure that `(n choose k) ≐ 0` when `n < k`.

## Formalization

```agda
binomial-coefficient-ℕ : ℕ → ℕ → ℕ
binomial-coefficient-ℕ zero-ℕ zero-ℕ = 1
binomial-coefficient-ℕ zero-ℕ (succ-ℕ k) = 0
binomial-coefficient-ℕ (succ-ℕ n) zero-ℕ = 1
binomial-coefficient-ℕ (succ-ℕ n) (succ-ℕ k) =
  (binomial-coefficient-ℕ n k) +ℕ (binomial-coefficient-ℕ n (succ-ℕ k))
```
