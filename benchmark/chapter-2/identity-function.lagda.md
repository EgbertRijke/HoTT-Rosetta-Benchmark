# The Identity Function

```agda
module chapter-2.identity-function where

open import universe-levels
```

## Statement

The **identity function** is a function `id : A → A` given by `id a ≔ a`.

## Formalization

```agda
id : {l : Level} {A : UU l} → A → A
id a = a
```

