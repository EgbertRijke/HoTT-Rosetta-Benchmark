# Negated Equality

```agda
module chapter-5.negated-equality where

open import universe-levels
open import chapter-4
open import chapter-5.identity-types
```

## Statement

The **negated equality** relation on a type `A` is the relation `_≠_` given by

```text
  x ≠ y ≔ ¬ (x ＝ y).
```

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  infix 6 _≠_

  _≠_ : A → A → UU l
  x ≠ y = ¬ (x ＝ y)
```
