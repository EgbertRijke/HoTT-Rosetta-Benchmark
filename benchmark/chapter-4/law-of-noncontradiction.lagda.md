# The Law of Noncontradiction

```agda
module chapter-4.law-of-noncontradiction where

open import universe-levels
open import chapter-4.cartesian-product-types
open import chapter-4.dependent-pair-types
open import chapter-4.negation
```

## Statement

The **law of noncontradiction** asserts that the type `A × ¬ A` is empty for all types `A`; that is, there is an element of type `¬ (A × ¬ A)`.

## Formalization

```agda
law-of-non-contradiction : {l : Level} {A : UU l} → ¬ (A × ¬ A)
law-of-non-contradiction (a , f) = f a
```
