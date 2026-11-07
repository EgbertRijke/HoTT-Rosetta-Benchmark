# Functoriality of Double Negation

```agda
module chapter-4.functoriality-double-negation where

open import universe-levels
open import chapter-4.double-negation
open import chapter-4.functoriality-negation
```

## Statement

Double negation acts functorially on types, in the sense that there is a function

```text
  (A → B) → ¬¬ A → ¬¬ B.
```

## Formalization

```agda
map-double-negation :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} → (A → B) → ¬¬ A → ¬¬ B
map-double-negation f = map-neg (map-neg f)
```
