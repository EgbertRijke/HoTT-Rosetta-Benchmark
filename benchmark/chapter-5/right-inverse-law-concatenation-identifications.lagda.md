# The Right Inverse Law for Concatenation of Identifications

```agda
module chapter-5.right-inverse-law-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
```

## Statement

The **right inverse law** for concatenation of identifications is an identification

```text
  p ∙ p⁻¹ ＝ refl
```

for any `p : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  right-inv : {x y : A} (p : x ＝ y) → p ∙ inv p ＝ refl
  right-inv refl = refl
```

