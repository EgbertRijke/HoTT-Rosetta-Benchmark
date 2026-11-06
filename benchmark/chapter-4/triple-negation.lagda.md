# Triple Negation

```agda
module chapter-4.triple-negation where

open import universe-levels
open import chapter-4.negation
open import chapter-4.double-negation
```

## Statement

The triple negation of a type `A` is defined to be the negation of its double negation.

## Formalization

```agda
infix 25 ¬¬¬_

¬¬¬_ : {l : Level} → UU l → UU l
¬¬¬ A = ¬ ¬¬ A
```
