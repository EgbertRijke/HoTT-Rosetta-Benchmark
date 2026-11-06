# Empty Types

```agda
module chapter-4.empty-types where

open import universe-levels
open import chapter-4.empty-type
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
