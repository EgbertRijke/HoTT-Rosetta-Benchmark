# The Right Unit Law for Right Whiskering With Respect to Concatenation of Identifications

```agda
module chapter-5.right-unit-law-right-whiskering-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.right-unit-law-concatenation-identifications
open import chapter-5.right-whiskering-concatenation-identifications
```

## Statement

The **right unit law** for right whiskering with respect to concatenation of identifications asserts that

```text
  right-whisker-concat α right ＝ α
```

for any identification `α : p ＝ q`, where `p q : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  right-unit-law-right-whisker-concat :
    {x y : A} {p p' : x ＝ y} (α : p ＝ p') →
    right-unit ∙ α ＝ right-whisker-concat α refl ∙ right-unit
  right-unit-law-right-whisker-concat {p = refl} refl = refl
```
