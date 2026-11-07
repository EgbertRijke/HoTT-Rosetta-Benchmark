# Evaluation

```agda
module chapter-2.evaluation where

open import universe-levels
```

## Statement

**Evaluation** at an element `a : A` is a function

```text
  ev : ((x : A) → B x) → B a.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : A → UU l2} (a : A)
  where

  ev : ((x : A) → B x) → B a
  ev f = f a
```
