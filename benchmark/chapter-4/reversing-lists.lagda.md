# Reversing of Lists

```agda
module chapter-4.reversing-lists where

open import universe-levels
open import chapter-4.concatenation-lists
open import chapter-4.lists
open import chapter-4.fold-operation-lists
```

## Statement

There is an operation `list A → list A` which reverses the order of the elements of a list

## Formalization

```agda
module _
  {l1 : Level} {A : UU l1}
  where

  reverse-list : list A → list A
  reverse-list nil = nil
  reverse-list (cons a l) = concat-list (reverse-list l) (cons a nil)
```
