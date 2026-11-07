# Postcomposition

```agda
module chapter-2.postcomposition where

open import universe-levels
open import chapter-2.composition
open import chapter-2.dependent-postcomposition
```

## Statement

Any map `f : A → B` induces a postcomposition function

```text
  (X → A) → (X → B).
```

## Formalization

```agda
module _
  {l1 l2 l3 : Level} (X : UU l1) {A : UU l2} {B : UU l3}
  where

  postcomp : (A → B) → (X → A) → (X → B)
  postcomp f = postcomp-Π X f
```
