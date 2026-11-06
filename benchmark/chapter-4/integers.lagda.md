# The Type of Integers

```agda
module chapter-4.integers where

open import universe-levels
open import chapter-3

open import chapter-4.coproduct-types
open import chapter-4.unit-type
```

## Statement

We define the **integers** to be the type `ℤ ≔ ℕ + (𝟙 + ℕ)`.
The type of integers comes equipped with inclusion functions of the positive and negative integers

```text
  in-pos-ℤ := inr ∘ inr : ℕ → ℤ
  in-neg-ℤ := inl       : ℕ → ℤ
```

and with the constants

```text
  -1_ℤ := in-neg-ℤ(0)
   0_ℤ := inr(inl(⋆))
   1_ℤ := in-pos-ℤ(0).
```

## Formalization

```agda
ℤ : UU lzero
ℤ = ℕ + (unit + ℕ)

{-# BUILTIN INTEGER ℤ #-}
```
