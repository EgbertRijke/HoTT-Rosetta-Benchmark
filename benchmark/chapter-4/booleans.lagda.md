# The Booleans

```agda
module chapter-4.booleans where

open import universe-levels
```

## Statement

The type of **booleans** is an inductive type `bool` that comes equipped with

```text
  false : bool
```

and

```text
  true : bool.
```

## Formalization

```agda
data bool : UU lzero where
  true false : bool

{-# BUILTIN BOOL bool #-}
{-# BUILTIN TRUE true #-}
{-# BUILTIN FALSE false #-}
```
