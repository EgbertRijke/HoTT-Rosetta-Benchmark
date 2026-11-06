# Multiplication on the Natural Numbers

```agda
module exercise-3-1-multiplication-natural-numbers where

open import section-3-1-natural-numbers
open import section-3-2-addition-natural-numbers
```

## Statement

Define the **multiplication** operation

```text
  mul-ℕ : ℕ → (ℕ → ℕ).
```

## Formalization

```agda
mul-ℕ : ℕ → ℕ → ℕ
mul-ℕ 0 n = 0
mul-ℕ (succ-ℕ m) n = (mul-ℕ m n) +ℕ n
```

## Syntax

```agda
infixl 40 _*ℕ_
_*ℕ_ = mul-ℕ

{-# BUILTIN NATTIMES _*ℕ_ #-}
```

