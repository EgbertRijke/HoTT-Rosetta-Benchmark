# Negation

```agda
module chapter-4.negation where

open import universe-levels
open import chapter-4.empty-type
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

