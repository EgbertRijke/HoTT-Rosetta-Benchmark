# Concatenation of List

```agda
module chapter-4.concatenation-lists where

open import universe-levels
open import chapter-4.lists
open import chapter-4.fold-operation-lists
```

## Statement

There is a binary operation `list A → list A → list A` which concatenates two lists into a single list.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  concat-list : list A → list A → list A
  concat-list l1 l2 = (fold-list l2 cons) l1
```
