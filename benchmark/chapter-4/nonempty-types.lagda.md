# Nonempty Types

```agda
module chapter-4.nonempty-types where

open import universe-levels
open import chapter-4.empty-types
```

## Statement

We say that a type `A` is nonempty the type `is-empty A` is itself empty.

## Formalization

```agda
is-nonempty : {l : Level} → UU l → UU l
is-nonempty A = is-empty (is-empty A)
```
