# The Left Unit Law for Left Whiskering With Respect to Concatenation of Identifications

```agda
module chapter-5.left-unit-law-left-whiskering-concatenation-identifications where

open import universe-levels
open import chapter-5.identity-types
open import chapter-5.left-whiskering-concatenation-identifications
```

## Statement

The **left unit law** for left whiskering with respect to concatenation of identifications asserts that

```text
  left-whisker-concat refl α ＝ α
```

for any identification `α : p ＝ q`, where `p q : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  left-unit-law-left-whisker-concat :
    {x y : A} {p q : x ＝ y} (α : p ＝ q) →
    left-whisker-concat refl α ＝ α
  left-unit-law-left-whisker-concat refl = refl
```
