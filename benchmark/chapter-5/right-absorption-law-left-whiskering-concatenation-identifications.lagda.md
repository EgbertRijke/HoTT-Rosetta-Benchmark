# The Right Absorption Law for Left Whiskering With Respect to Concatenation of Identifications

```agda
module chapter-5.right-absorption-law-left-whiskering-concatenation-identifications where

open import universe-levels
open import chapter-5.identity-types
open import chapter-5.left-whiskering-concatenation-identifications
```

## Statement

The **right absorption law** for left whiskering with respect to concatenation of identifications asserts that

```text
  left-whisker-concat p refl ＝ refl
```

for any `p : x ＝ y` and `q : y ＝ z`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  right-absorption-law-left-whisker-concat :
    {x y z : A} (p : x ＝ y) (q : y ＝ z) →
    left-whisker-concat p (refl {x = q}) ＝ refl
  right-absorption-law-left-whisker-concat p q = refl
```

