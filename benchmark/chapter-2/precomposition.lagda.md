# Precomposition

```agda
module chapter-2.precomposition where

open import universe-levels
open import chapter-2.composition
```

## Statement

Any map `f : A → B` induces a precomposition function

```text
  (B → C) → (A → C).
```

## Formalization

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} (f : A → B) (C : UU l3)
  where

  precomp : (B → C) → (A → C)
  precomp = _∘ f
```
