# The successor function on the integers

```agda
module chapter-4.successor-function-integers where

open import chapter-3
open import chapter-4.coproduct-types
open import chapter-4.integers
open import chapter-4.one-integer
open import chapter-4.zero-integer
```

## Statement

We define the **successor function** on the integers `succ-ℤ : ℤ → ℤ` using the split induction principle, taking

```text
  succ-ℤ(-1_ℤ)                ≔ 0_ℤ
  succ-ℤ(in-neg-ℤ(succ-ℕ(n))) ≔ in-neg-ℤ(n)
  succ-ℤ(0_ℤ)                 ≔ 1_ℤ
  succ-ℤ(1_ℤ)                 ≔ in-pos-ℤ(1_ℕ)
  succ-ℤ(in-pos-ℤ(succ-ℕ(n))) ≔ in-pos-ℤ(succ-ℕ(succ-ℕ(n))).
```

## Formalization

```agda
succ-ℤ : ℤ → ℤ
succ-ℤ (inl zero-ℕ) = zero-ℤ
succ-ℤ (inl (succ-ℕ x)) = inl x
succ-ℤ (inr (inl _)) = one-ℤ
succ-ℤ (inr (inr x)) = inr (inr (succ-ℕ x))
```
