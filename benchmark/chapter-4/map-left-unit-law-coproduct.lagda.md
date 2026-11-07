# The Underlying Map of the Left Unit Law of Coproducts

```agda
module chapter-4.map-left-unit-law-coproduct where

open import universe-levels
open import chapter-4.empty-types
open import chapter-4.ex-falso
open import chapter-4.coproduct-types
```

## Statement

Consider two types `A` and `B`, and suppose that `A` is empty. Then there is a function

```text
  (A + B) → B.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (H : is-empty A)
  where

  map-left-unit-law-coproduct : A + B → B
  map-left-unit-law-coproduct (inl a) = ex-falso (H a)
  map-left-unit-law-coproduct (inr b) = b
```

## Proof

We will construct the function `(A + B) → B` with the induction principle of the coproduct `A + B`. Therefore, we must construct two functions:

```text
  f : A → B
  g : B → B.
```

The function `g` is simply defined to be the identity function `id : B → B`. Recall that we have assumed that `A` is empty, so we have a function `H : A → ∅`. Furthermore, we always have the function `ex-falso : ∅ → B`. Therefore, we can define `f ≔ ex-falso ∘ H` to complete the proof.
