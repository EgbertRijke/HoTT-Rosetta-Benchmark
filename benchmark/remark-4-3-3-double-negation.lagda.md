# Double Negation

```agda
module remark-4-3-3-double-negation where

open import universe-levels
open import definition-4-3-2-negation
```

## Statement

The double negation of a type `A` is defined to be the negation of its negation.

## Formalization

```agda
infix 25 ¬¬_

¬¬_ : {l : Level} → UU l → UU l
¬¬ A = ¬ ¬ A
```
