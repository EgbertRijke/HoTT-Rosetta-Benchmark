# The Left Unit Law for Concatenation of Identifications

```agda
module chapter-5.left-unit-law-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

The **left unit law** for concatenation of identifications is an identification

```text
  refl ∙ p ＝ p
```

for any `p : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  left-unit : {x y : A} {p : x ＝ y} → refl ∙ p ＝ p
  left-unit = refl
```
