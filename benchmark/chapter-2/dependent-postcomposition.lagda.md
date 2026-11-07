# Dependent Postcomposition

```agda
module chapter-2.dependent-postcomposition where

open import universe-levels
open import chapter-2.composition
```

## Statement

Any family of maps `f : {i : I} → A i → B i` induces a postcomposition function

```text
  ((i : I) → A i) → ((i : I) → B i).
```

## Formalization

```agda
module _
  {l1 l2 l3 : Level} (I : UU l1) {A : I → UU l2} {B : I → UU l3}
  where

  postcomp-Π : ({i : I} → A i → B i) → ((i : I) → A i) → ((i : I) → B i)
  postcomp-Π f = f ∘_
```
