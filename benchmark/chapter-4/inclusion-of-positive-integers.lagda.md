# The Inclusion of the Positive Integers

```agda
module chapter-4.inclusion-of-positive-integers where

open import chapter-3
open import chapter-4.coproduct-types
open import chapter-4.integers
```

## Statement

The inclusion of the positive integers is the function `inr ∘ inr : ℕ → ℤ`.

## Formalization

```agda
in-pos-ℤ : ℕ → ℤ
in-pos-ℤ n = inr (inr n)
```
