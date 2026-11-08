# The Injectivity of Based Preconcatenation of Identifications

```agda
module chapter-5.injectivity-based-preconcatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

The based preconcatenation operation `y ＝ z → x ＝ z` is injective for any identification `p : x ＝ y`.

## Formalization

```agda
module _
  {l1 : Level} {A : UU l1}
  where

  is-injective-concat :
    {x y z : A} (p : x ＝ y) {q r : y ＝ z} → p ∙ q ＝ p ∙ r → q ＝ r
  is-injective-concat refl s = s
```

