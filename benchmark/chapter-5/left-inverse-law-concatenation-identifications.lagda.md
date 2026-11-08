# The Left Inverse Law for Concatenation of Identifications

```agda
module chapter-5.left-inverse-law-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
```

## Statement

The **left inverse law** for concatenation of identifications is an identification

```text
  p⁻¹ ∙ p ＝ refl
```

for any `p : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  left-inv : {x y : A} (p : x ＝ y) → inv p ∙ p ＝ refl
  left-inv refl = refl
```

