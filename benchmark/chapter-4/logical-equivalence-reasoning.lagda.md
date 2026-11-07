# Logical Equivalence Reasoning

```agda
module chapter-4.logical-equivalence-reasoning where

open import universe-levels
open import chapter-2
open import chapter-4.composition-logical-equivalences
open import chapter-4.dependent-pair-types
open import chapter-4.logical-equivalences
```

## Statement

**Logical equivalence reasoning** is reasoning by chaining logical equivalences together. For example, the following chain of logical equivalences

```text
  A ↔ B
    ↔ C
    ↔ D
```

shows that `A ↔ D`.

## Formalization

```agda
infixl 1 logical-equivalence-reasoning_
infixl 0 step-logical-equivalence-reasoning

logical-equivalence-reasoning_ :
  {l1 : Level} (X : UU l1) → X ↔ X
pr1 (logical-equivalence-reasoning X) = id
pr2 (logical-equivalence-reasoning X) = id

step-logical-equivalence-reasoning :
  {l1 l2 l3 : Level} {X : UU l1} {Y : UU l2} →
  (X ↔ Y) → (Z : UU l3) → (Y ↔ Z) → (X ↔ Z)
step-logical-equivalence-reasoning e Z f = f ∘iff e

syntax step-logical-equivalence-reasoning e Z f = e ↔ Z by f
```
