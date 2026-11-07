# Binary Functoriality Double Negation

```agda
module chapter-4.binary-functoriality-double-negation where

open import universe-levels
open import chapter-2
open import chapter-4.double-negation
open import chapter-4.functoriality-double-negation
open import chapter-4.double-negation-elimination-function-types
```

## Statement

Any binary operation `f : A → B → C` induces a binary operation

```text
  ¬¬ f : ¬¬ A → ¬¬ B → ¬¬ C
```

## Formalization

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {C : UU l3}
  (f : A → B → C)
  where

  binary-map-double-negation :
    ¬¬ A → ¬¬ B → ¬¬ C
  binary-map-double-negation =
    ( λ b → double-negation-elimination-function-type b) ∘
    ( map-double-negation (λ a → map-double-negation (f a)))
```
