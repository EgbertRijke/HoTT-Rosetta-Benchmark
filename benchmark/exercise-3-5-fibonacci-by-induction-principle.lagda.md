# The Fibonacci Sequence by the Induction Principle

```agda
module exercise-3-5-fibonacci-by-induction-principle where

open import section-3-1-natural-numbers
open import section-3-1-induction-natural-numbers
open import section-3-2-addition-natural-numbers
```

## Statement

Use the induction principle of `ℕ` to define the **Fibonacci sequence** as a function `F : ℕ → ℕ` that satisfies the equations

```text 
                  F(0) ≐ 0 
                  F(1) ≐ 1 
  F(succ-ℕ(succ-ℕ(n))) ≐ F(succ-ℕ(n)) + F(n)
```

## Remark

This exercise specifically asks the solver to use `ind-ℕ`; the usual definition by pattern matching therefore doesn't count as a solution.

## Formalization

```agda
function-inductive-fibonacci : ℕ → ℕ → ℕ → ℕ
function-inductive-fibonacci =
  ind-ℕ
    ( λ a b → a)
    ( λ _ f a b → f b (b +ℕ a))

inductive-fibonacci : ℕ → ℕ
inductive-fibonacci n = function-inductive-fibonacci n 0 1
```
