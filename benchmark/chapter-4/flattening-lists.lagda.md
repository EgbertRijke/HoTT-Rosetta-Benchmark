# Flattening of Lists

```agda
module chapter-4.flattening-lists where

open import universe-levels
open import chapter-4.concatenation-lists
open import chapter-4.lists
open import chapter-4.fold-operation-lists
```

## Statement

There is an operation `list (list A) → list A` which concatenates any list of lists into a single list.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  flatten-list : list (list A) → list A
  flatten-list = fold-list nil concat-list
```
