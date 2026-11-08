# The Injectivity of Based Postconcatenation of Identifications

```agda
module chapter-5.injectivity-based-postconcatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.right-unit-law-concatenation-identifications
```

## Statement

The based postconcatenation operation `x ＝ y → x ＝ z` is injective for any identification `q : y ＝ z`.

## Formalization

```agda
module _
  {l1 : Level} {A : UU l1}
  where

  is-injective-concat' :
    {x y z : A} (r : y ＝ z) {p q : x ＝ y} → p ∙ r ＝ q ∙ r → p ＝ q
  is-injective-concat' refl s = inv right-unit ∙ s ∙ right-unit
```

