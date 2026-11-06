# Triple Negation

```agda
module remark-4-3-3-triple-negation where

open import universe-levels
open import definition-4-3-2-negation
open import remark-4-3-3-double-negation
```

## Statement

The triple negation of a type `A` is defined to be the negation of its double negation.

## Formalization

```agda
infix 25 ¬¬¬_

¬¬¬_ : {l : Level} → UU l → UU l
¬¬¬ A = ¬ ¬¬ A
```
