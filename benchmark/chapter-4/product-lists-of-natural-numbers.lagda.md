# The Product of a List of Natural Numbers

```agda
module chapter-4.product-lists-of-natural-numbers where

open import chapter-3
open import chapter-4.lists
open import chapter-4.fold-operation-lists
```

## Statement

There is a function `list ℕ → ℕ` which returns the product of numbers in a list of natural numbers.

## Formalization

```agda
product-list-ℕ : list ℕ → ℕ
product-list-ℕ = fold-list 1 _*ℕ_
```
