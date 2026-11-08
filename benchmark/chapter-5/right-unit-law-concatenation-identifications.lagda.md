# The Right Unit Law for Concatenation of Identifications

```agda
module chapter-5.right-unit-law-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

The **right unit law** for concatenation of identifications is an identification

```text
  p ∙ refl ＝ p
```

for any `p : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  right-unit : {x y : A} {p : x ＝ y} → p ∙ refl ＝ p
  right-unit {p = refl} = refl
```
