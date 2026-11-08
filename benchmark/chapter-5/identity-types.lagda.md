# Identity Types

```agda
module chapter-5.identity-types where

open import universe-levels
```

## Statement

The identity type on a type `A` with a distinguished element `a` is an inductive type family `a ＝_ : A → 𝒰` with one generator

```text
  refl : a ＝ a.
```

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  infix 6 _＝_

  data _＝_ (x : A) : A → UU l where
    instance refl : x ＝ x

{-# BUILTIN EQUALITY _＝_ #-}
```


