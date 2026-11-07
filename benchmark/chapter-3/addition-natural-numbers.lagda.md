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
infixl 35 _+ℕ_

_+ℕ_ : ℕ → ℕ → ℕ
x +ℕ 0 = x
x +ℕ succ-ℕ y = succ-ℕ (x +ℕ y)

{-# BUILTIN NATPLUS _+ℕ_ #-}
```
