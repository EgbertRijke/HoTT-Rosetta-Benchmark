# The Length of a List

```agda
module chapter-4.length-lists where

open import universe-levels
open import chapter-3
open import chapter-4.lists
open import chapter-4.fold-operation-lists
```

## Statement

There is a function `list A → ℕ` which returns the number of elements in a list.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  length-list : list A → ℕ
  length-list = fold-list 0 (λ a → succ-ℕ)
```
