# The Sum of a List of Natural Numbers

```agda
module chapter-4.sum-lists-of-natural-numbers where

open import chapter-3
open import chapter-4.lists
open import chapter-4.fold-operation-lists
```

## Statement

There is a function `list ℕ → ℕ` which returns the sum of numbers in a list of natural numbers.

## Formalization

```agda
sum-list-ℕ : list ℕ → ℕ
sum-list-ℕ = fold-list 0 _+ℕ_
```
