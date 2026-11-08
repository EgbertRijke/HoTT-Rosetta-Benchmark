# Left Unwhiskering With Respect to Concatenation of Identifications

```agda
module chapter-5.left-unwhiskering-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.injectivity-based-preconcatenation-identifications
```

## Statement

The **left unwhiskering operation** with respect to concatenation of identifications is a function

```text
  (p ∙ q ＝ p ∙ r) → (q ＝ r)
```

for any identification `p : x ＝ y` and any pair of identifications `q r : y ＝ z`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  left-unwhisker-concat :
    {x y z : A} (p : x ＝ y) {q r : y ＝ z} → p ∙ q ＝ p ∙ r → q ＝ r
  left-unwhisker-concat = is-injective-concat
```
