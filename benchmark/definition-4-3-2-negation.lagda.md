# Negation

```agda
module definition-4-3-2-negation where

open import universe-levels
open import definition-4-3-1-empty-type
```

## Statement

For any type `A` we define **negation** of `A` by

```text
  ¬ A ≔ A → ∅.
```

## Formalization

```agda
infix 25 ¬_

¬_ : {l : Level} → UU l → UU l
¬ A = A → empty
```

