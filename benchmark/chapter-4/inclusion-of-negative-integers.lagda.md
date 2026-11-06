# The Inclusion of the Negative Integers

```agda
module chapter-4.inclusion-of-negative-integers where

open import chapter-3

open import chapter-4.coproduct-types
open import chapter-4.integers
```

## Statements

The inclusion of the negative integers is the function `inl : ℕ → ℤ`.

## Formalization

```agda
in-neg-ℤ : ℕ → ℤ
in-neg-ℤ n = inl n
```
