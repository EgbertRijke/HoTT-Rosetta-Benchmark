# Division by Two

```agda
module chapter-3.division-by-two where

open import chapter-3.natural-numbers
```

## Statement

Define division by two rounded down as a function `ℕ → ℕ` by pattern matching.

## Formalization

```agda
division-by-two : ℕ → ℕ
division-by-two zero-ℕ = 0
division-by-two (succ-ℕ zero-ℕ) = 0
division-by-two (succ-ℕ (succ-ℕ n)) = succ-ℕ (division-by-two n)
```


