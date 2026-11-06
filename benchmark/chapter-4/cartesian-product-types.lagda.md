# Cartesian Product Types

```agda
module chapter-4.cartesian-product-types where

open import universe-levels
open import chapter-4.dependent-pair-types
```

## Statement

Given two types `A` and `B`, the **cartesian product** `A × B` is defined as

```text
  A × B ≔ Σ A (λ x → B).
```

## Formalization

```agda
infixr 15 _×_

_×_ : {l1 l2 : Level} (A : UU l1) (B : UU l2) → UU (l1 ⊔ l2)
A × B = Σ A (λ x → B)
```
