# Ex Falso Quodlibet

```
module chapter-4.ex-falso where

open import universe-levels
open import chapter-4.empty-type
```

## Statement

For each type `A`, we define the function `ex-falso : ∅ → A` by the induction principle of the empty type.

## Formalization

```agda
ex-falso : {l : Level} {A : UU l} → empty → A
ex-falso = ind-empty
```
