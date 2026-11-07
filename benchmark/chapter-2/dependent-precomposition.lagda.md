# Dependent Precomposition

```agda
module chapter-2.dependent-precomposition where

open import universe-levels
```

## Statement

Any map `f : A → B` induces a precomposition function

```text
  ((b : B) → C b) → ((a : A) → C (f a)).
```

## Formalization

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} (f : A → B) (C : B → UU l3)
  where

  precomp-Π : ((b : B) → C b) → ((a : A) → C (f a))
  precomp-Π h a = h (f a)
```
