# Uncurrying

```agda
module chapter-4.uncurrying where

open import universe-levels
open import chapter-4.dependent-pair-types
```

## Statement

The **uncurrying** operation is the evaluation map

```text
  ((t : Σ A B) → C t) → ((x : A) (y : B x) → C (x , y)).
```

## Formalization

```agda
ev-pair :
  {l1 l2 l3 : Level} {A : UU l1} {B : A → UU l2} {C : Σ A B → UU l3} →
  ((t : Σ A B) → C t) → (x : A) (y : B x) → C (x , y)
ev-pair f x y = f (x , y)
```
