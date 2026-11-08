# The Left Absorption Law for Right Whiskering With Respect to Concatenation of Identifications

```agda
module chapter-5.left-absorption-law-right-whiskering-concatenation-identifications where

open import universe-levels
open import chapter-5.identity-types
open import chapter-5.right-whiskering-concatenation-identifications
```

## Statement

The **left absorption law** for right whiskering with respect to concatenation of identifications asserts that

```text
  right-whisker-concat refl q ＝ refl
```

for any `p : x ＝ y` and `q : y ＝ z`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  left-absorption-law-right-whisker-concat :
    {x y z : A} (p : x ＝ y) (q : y ＝ z) →
    right-whisker-concat (refl {x = p}) q ＝ refl
  left-absorption-law-right-whisker-concat p q = refl
```

