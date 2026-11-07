# Addition on the Natural Numbers

```agda
module chapter-3.addition-natural-numbers where

open import chapter-3.natural-numbers
```

## Statement

Define a function

```text
  add-ℕ : ℕ → (ℕ → ℕ)
```

satisfying the specification

```text
          add-ℕ(m,0) ≐ m,
  add-ℕ(m,succ-ℕ(n)) ≐ succ-ℕ(add-ℕ(m,n)).
```

Introduce the notation `m + n` for `add-ℕ(m,n)`.

## Formalization

```agda
add-ℕ : ℕ → ℕ → ℕ
add-ℕ x 0 = x
add-ℕ x (succ-ℕ y) = succ-ℕ (add-ℕ x y)

infixl 35 _+ℕ_
_+ℕ_ = add-ℕ

{-# BUILTIN NATPLUS _+ℕ_ #-}
```
