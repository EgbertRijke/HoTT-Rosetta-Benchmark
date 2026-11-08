# Left Whiskering With Respect to Concatenation of Identifications

```agda
module chapter-5.left-whiskering-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

The **left whiskering operation** with respect to concatenation of identifications is a function

```text
  (q ＝ r) → (p ∙ q ＝ p ∙ r)
```

for any identification `p : x ＝ y` and any pair of identifications `q r : y ＝ z`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  left-whisker-concat :
    {x y z : A} (p : x ＝ y) {q r : y ＝ z} → q ＝ r → p ∙ q ＝ p ∙ r
  left-whisker-concat p refl = refl
```
