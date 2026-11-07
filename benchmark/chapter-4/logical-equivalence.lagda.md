# Logical Equivalence of Types

```agda
module chapter-4.logical-equivalence where

open import universe-levels
open import chapter-4.cartesian-product-types
open import chapter-4.dependent-pair-types
```

## Statement

Two types `A` and `B` are said to be **logically equivalent** if there are functions back and forth between the two; that is, if there is an element of type

```text
  A ↔ B ≔ (A → B) × (B → A).
```

## Remark

When introducing a structured type, it is customary to write semantic projections. We will include these in the formalization.

## Formalization

```agda
infix 6 _↔_

_↔_ : {l1 l2 : Level} (A : UU l1) (B : UU l2) → UU (l1 ⊔ l2)
A ↔ B = (A → B) × (B → A)

module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (H : A ↔ B)
  where

  forward-implication : A → B
  forward-implication = pr1 H

  backward-implication : B → A
  backward-implication = pr2 H
```
