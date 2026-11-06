# Division by Two by the Induction Principle

```agda
module exercise-3-6-division-by-two-by-induction-principle where

open import section-3-1-natural-numbers
open import section-3-1-recursion-natural-numbers
```

## Statement

Define division by two rounded down as a function `ℕ → ℕ` by the induction principle of `ℕ`.

## Remark

This exercise specifically asks the solver to use `ind-ℕ`; the easier definition by pattern matching therefore doesn't count as a solution. Since `rec-ℕ` is defined as an instance of `ind-ℕ`, we permit ourselves to use `rec-ℕ`.

## Formalization

```agda
div-two-ℕ : ℕ → ℕ
div-two-ℕ n =
  rec-ℕ (λ a b → a) (λ _ f a b → f b (succ-ℕ a)) n 0 0
```
