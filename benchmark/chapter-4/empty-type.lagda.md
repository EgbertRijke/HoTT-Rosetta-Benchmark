# The Empty Type

```agda
module chapter-4.empty-type where

open import universe-levels
```

## Statement

The **empty type** is defined to be a type `∅` satisfying the induction principle that for any family of types `P(x)` indexed by `x : ∅`, there is a dependent function

```text
  ind_∅ : Π(x : ∅) P(x).
```

## Formalization

```agda
data empty : UU lzero where

ind-empty : {l : Level} {P : empty → UU l} → ((x : empty) → P x)
ind-empty ()
```
