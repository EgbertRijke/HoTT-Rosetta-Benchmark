# Lists

```agda
module chapter-4.lists where

open import universe-levels
```

## Statement

For any type `A`, we define the type `list(A)` of **lists** of elements of `A` as the inductive type with constructors

```text
  nil : list(A)
  cons : A → (list(A) → list(A))
```

## Formalization

```agda
data list {l : Level} (A : UU l) : UU l where
  nil : list A
  cons : A → list A → list A

{-# BUILTIN LIST list #-}
```
