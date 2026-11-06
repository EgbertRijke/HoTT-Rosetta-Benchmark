# Addition on the Natural Numbers

```agda
module section-3-2-addition-natural-numbers where

open import section-3-1-natural-numbers
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

## Construction

We will construct the binary operation `add-ℕ : ℕ → (ℕ → ℕ)` by induction on the second variable.
In other words, we will construct an element

```text
  m : ℕ ⊢ add-ℕ(m) : ℕ → ℕ.
```

The induction principle of `ℕ` is used with the family of types `P(n) ≔ ℕ` indexed by `n : ℕ` in context `m : ℕ`.
Therefore, we need to construct

```text
  m : ℕ ⊢ add-0 (m) : ℕ,
  m : ℕ ⊢ add-S (m) : ℕ → (ℕ → ℕ),
```

in order to obtain

```text
  m : ℕ ⊢ add-ℕ(m) ≔ ind-ℕ(add - 0(m),add-S(m)) : ℕ → ℕ.
```

The element `add-0(m) : ℕ` in context `m : ℕ` is of course defined to be `m : ℕ`, i.e., by the generic element, because adding zero should just be the identity function.
To see how the function `add-S(m) : ℕ → (ℕ → ℕ)` should be defined, we look at the specification of `add-ℕ(m)` when it is applied to a successor:

```text
  add-ℕ(m,succ-ℕ(n)) ≐ succ-ℕ(add-ℕ(m,n)).
```

This shows us that we should define

```text
  add-S(m,n,x) ≐ succ-ℕ(x),
```

because with this definition we will have

```text
  add-ℕ(m,succ-ℕ(n)) ≐ ind-ℕ(add - 0(m),add-S(m),succ-ℕ(n))
                     ≐ add-S(m,n,add-ℕ(m,n))
                     ≐ succ-ℕ(add-ℕ(m,n)).
```

The formal derivation for the construction of `add-S` is as follows:

```text
                ----------  ------------------
                 ⊢ ℕ type    ⊢ succ-ℕ : ℕ → ℕ
  ----------    ------------------------------
   ⊢ ℕ type       n : ℕ ⊢ succ-ℕ : ℕ → ℕ
  --------------------------------------------
          m : ℕ, n : ℕ ⊢ succ-ℕ : ℕ → ℕ
  --------------------------------------------
       m : ℕ ⊢ λ n. succ-ℕ : ℕ → (ℕ → ℕ)
  ----------------------------------------------
   m : ℕ ⊢ add-S(m) ≔ λ n. succ-ℕ : ℕ → (ℕ → ℕ).
```

We combine this derivation with the induction principle of `ℕ` to complete the construction of addition:

```text
               ⋮                               ⋮
  --------------------------  --------------------------------
   m : ℕ ⊢ add - 0(m) ≔ m : ℕ    m : ℕ ⊢ add-S(m) : ℕ → (ℕ → ℕ)
  ------------------------------------------------------------
      m : ℕ ⊢ ind-ℕ(add - 0(m),add-S(m)) : ℕ → ℕ
    -----------------------------------------------------
     m : ℕ ⊢ add-ℕ(m) ≔ ind-ℕ(add - 0(m),add-S(m)) : ℕ → ℕ
```

The asserted judgmental equalities then hold by the computation rules for `ℕ`. □

## Agda Formalization

```agda
add-ℕ : ℕ → ℕ → ℕ
add-ℕ x 0 = x
add-ℕ x (succ-ℕ y) = succ-ℕ (add-ℕ x y)

infixl 35 _+ℕ_
_+ℕ_ = add-ℕ

{-# BUILTIN NATPLUS _+ℕ_ #-}
```
