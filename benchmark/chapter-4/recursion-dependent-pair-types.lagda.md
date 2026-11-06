# The Recursion Principle of Dependent Pair Types

```agda
module chapter-4.recursion-dependent-pair-types where

open import universe-levels
open import chapter-4.dependent-pair-types
```

## Statement

The recursion principle of dependent pair types asserts that for every type `C` there is a function

```text
  ((x : A) (y : B x) → C) → Σ A B → C.
```

## Formalization

```agda
rec-Σ :
  {l1 l2 l3 : Level} {A : UU l1} {B : A → UU l2} {C : UU l3} →
  ((x : A) (y : B x) → C) → Σ A B → C
rec-Σ f (x , y) = f x y
```
