# Empty Types

```agda
module definition-4-3-2-empty-types where

open import universe-levels
open import definition-4-3-1-empty-type
```

## Statement

We say that a type `A` is empty if there is an element of type

```text
  is-empty A ≔ A → ∅.
```

## Formalization

```agda
is-empty : {l : Level} → UU l → UU l
is-empty A = A → empty
```
