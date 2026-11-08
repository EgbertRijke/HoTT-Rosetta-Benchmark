# The Associator for Concatenation of Identifications

```agda
module chapter-5.associator-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

The **associator** for concatenation of identifications is an identification

```text
  (p ∙ q) ∙ r ＝ p ∙ (q ∙ r)
```

for any `p : x ＝ y`, `q : y ＝ z`, and `r : z ＝ w`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  assoc :
    {x y z w : A} (p : x ＝ y) (q : y ＝ z) (r : z ＝ w) →
    (p ∙ q) ∙ r ＝ p ∙ (q ∙ r)
  assoc refl q r = refl
```
