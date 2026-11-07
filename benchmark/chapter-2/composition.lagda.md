# Composition

```agda
module chapter-2.composition where

open import universe-levels
```

## Statement

Given a binary dependent function `g : {a : A} (b : B a) → C a b` and an ordinary dependent function `f : (a : A) → B a`, their composite `g ∘ f` given by `a ↦ g (f a)` is a dependent function

```text
  (a : A) → C a (f a).
```

## Formalization

```agda
infixr 15 _∘_

_∘_ :
  {l1 l2 l3 : Level}
  {A : UU l1} {B : A → UU l2} {C : (a : A) → B a → UU l3} →
  ({a : A} → (b : B a) → C a b) → (f : (a : A) → B a) → (a : A) → C a (f a)
(g ∘ f) a = g (f a)
```
