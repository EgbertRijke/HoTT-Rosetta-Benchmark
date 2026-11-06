# The Underlying Map of the Right Unit Law of Coproducts

```agda
module chapter-4.map-right-unit-law-coproduct where

open import universe-levels
open import chapter-4.empty-types
open import chapter-4.ex-falso
open import chapter-4.coproduct-types
```

## Statement

Consider two types `A` and `B`, and suppose that `B` is empty. Then there is a function

```text
  (A + B) → A.
```

## Proof

We will construct the function `(A + B) → A` with the induction principle of the coproduct `A + B`. Therefore, we must construct two functions:

```text
  f : A → A
  g : B → A.
```

The function `f` is simply defined to be the identity function `id : A → A`. Recall that we have assumed that `B` is empty, so we have a function `H : B → ∅`. Furthermore, we always have the function `ex-falso : ∅ → A`. Therefore, we can define `g ≔ ex-falso ∘ H` to complete the proof.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (H : is-empty B)
  where

  map-right-unit-law-coproduct : A + B → A
  map-right-unit-law-coproduct (inl a) = a
  map-right-unit-law-coproduct (inr b) = ex-falso (H b)
```
