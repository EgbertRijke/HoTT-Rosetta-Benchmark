# Functoriality of Coproduct Types

```agda
module chapter-4.functoriality-coproduct-types where

open import universe-levels
open import chapter-4.coproduct-types
```

## Statement

The functorial action of the coproduct type constructor on maps determines for each `f : A → A'` and each `g : B → B'` a map `f + g : A + B → A' + B'` defined by

```text
  (f + g)(inl(x)) ≔ inl(f(x))
  (f + g)(inr(y)) ≔ inr(g(y)).
```

## Formalization

```agda
map-coproduct :
  {l1 l2 l3 l4 : Level}
  {A : UU l1} {B : UU l2} {A' : UU l3} {B' : UU l4}
  (f : A → A') (g : B → B') → A + B → A' + B'
map-coproduct f g (inl x) = inl (f x)
map-coproduct f g (inr y) = inr (g y)
```
