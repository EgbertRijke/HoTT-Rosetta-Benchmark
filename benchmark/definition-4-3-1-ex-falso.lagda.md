# Ex Falso Quodlibet

```
module definition-4-3-1-ex-falso where

open import universe-levels
open import definition-4-3-1-empty-type
```

## Statement

For each type `A`, we define the function `ex-falso : ∅ → A` by the induction principle of the empty type.

## Formalization

```agda
ex-falso : {l : Level} {A : UU l} → empty → A
ex-falso = ind-empty
```
