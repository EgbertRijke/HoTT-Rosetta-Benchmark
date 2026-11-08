# Right Whiskering With Respect to Concatenation of Identifications

```agda
module chapter-5.right-whiskering-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

The **right whiskering operation** with respect to concatenation of identifications is a function

```text
  (p ＝ q) → (r : y ＝ z) → (p ∙ r ＝ q ∙ r)
```

for any pair of identifications `p q : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  right-whisker-concat :
    {x y z : A} {p q : x ＝ y} → p ＝ q →  (r : y ＝ z) → p ∙ r ＝ q ∙ r
  right-whisker-concat refl α = refl
```
