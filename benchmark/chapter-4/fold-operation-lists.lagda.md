# The Fold Operation on Lists

```agda
module chapter-4.fold-operation-lists where

open import universe-levels
open import chapter-4.lists
```

## Statement

Let `A` and `B` be types with `b : B`, and consider a binary operation `μ : A → (B → B)`. Then there is a function

```text
  fold-list(μ) : list(A) → B
```

that iterates the operation `μ`, starting with `fold-list(μ,nil) ≔ b`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (b : B)
  (μ : A → B → B)
  where

  fold-list : list A → B
  fold-list nil = b
  fold-list (cons a l) = μ a (fold-list l)
```
