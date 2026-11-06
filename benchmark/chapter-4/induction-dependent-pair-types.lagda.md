# The Induction Principle of Dependent Pair Types

```agda
module chapter-4.induction-dependent-pair-types where

open import universe-levels
open import chapter-4.dependent-pair-types
```

## Statement

The induction principle of dependent pair types asserts that for every type family `C : Σ A B → 𝒰` there is a function

```text
  ((x : A) (y : B x) → C (x , y)) → (t : Σ A B) → C t.
```

## Formalization

```agda
ind-Σ :
  {l1 l2 l3 : Level} {A : UU l1} {B : A → UU l2} {C : Σ A B → UU l3} →
  ((x : A) (y : B x) → C (x , y)) → (t : Σ A B) → C t
ind-Σ f (x , y) = f x y
```
