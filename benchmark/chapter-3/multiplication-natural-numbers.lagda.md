# Multiplication on the Natural Numbers

```agda
module chapter-3.multiplication-natural-numbers where

open import chapter-3.natural-numbers
open import chapter-3.addition-natural-numbers
```

## Statement

Define the **multiplication** operation

```text
  mul-ℕ : ℕ → ℕ → ℕ.
```

## Formalization

```agda
infixl 40 _*ℕ_

_*ℕ_ : ℕ → ℕ → ℕ
0 *ℕ n = 0
succ-ℕ m *ℕ n = (m *ℕ n) +ℕ n

{-# BUILTIN NATTIMES _*ℕ_ #-}
```

