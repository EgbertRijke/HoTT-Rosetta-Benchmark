# The Unit Type

```agda
module chapter-4.unit-type where

open import universe-levels
```

## Statement

The **unit type** is defined to be a type `unit` equipped with a term

```text
  ⋆ : unit,
```

satisfying the induction principle that for any family of types `P(x)` indexed by `x : unit`, there is a function

```text
  ind-unit : P(⋆) → Π(x : unit) P(x)
```

for which the computation rule

```text
  ind-unit(p,⋆) ≐ p
```

holds.

## Formalization

```agda
record unit : UU lzero where
  instance constructor star

{-# BUILTIN UNIT unit #-}

ind-unit : {l : Level} {P : unit → UU l} → P star → (x : unit) → P x
ind-unit p star = p
```

