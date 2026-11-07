# Functoriality of List

```agda
module chapter-4.functoriality-lists where

open import universe-levels
open import chapter-4.lists
open import chapter-4.fold-operation-lists
```

## Statement

Any function `A → B` induces a function `list A → list B`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (f : A → B)
  where

  map-list : list A → list B
  map-list = fold-list nil (λ a → cons (f a))
```
