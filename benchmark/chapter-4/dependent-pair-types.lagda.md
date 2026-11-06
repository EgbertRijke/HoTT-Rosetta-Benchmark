# Dependent Pair Types

```agda
module chapter-4.dependent-pair-types where

open import universe-levels
```

## Statement

Consider a type family `B` over `A`.
The **dependent pair type** (or **`Σ`-type**) is defined to be the inductive
type `Σ(x : A) B(x)` equipped with a **pairing function**

```text
  _,_ : Π(x : A) (B(x) → Σ(y : A) B(y)).
```

## Remark

We follow the convention of agda-unimath and define `Σ A B` as a **record type**, even though the natural language specification declares dependent pair types to be inductive.

## Formalization

```agda
infixr 3 _,_

record Σ {l1 l2 : Level} (A : UU l1) (B : A → UU l2) : UU (l1 ⊔ l2) where
  constructor _,_
  field
    pr1 : A
    pr2 : B pr1

open Σ public

{-# BUILTIN SIGMA Σ #-}
{-# INLINE _,_ #-}
```
