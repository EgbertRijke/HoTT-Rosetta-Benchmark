# Multiplication on the Natural Numbers

```agda
module chapter-3.multiplication-natural-numbers where

open import chapter-3.natural-numbers
open import chapter-3.addition-natural-numbers
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

