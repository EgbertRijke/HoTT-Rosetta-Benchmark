# Transposing Inverse Identifications along Identifications

```agda
module chapter-5.transposing-inverse-identifications-along-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.right-unit-law-concatenation-identifications
```

## Statement

An identification `q ＝ inv p ∙ r` can be proven by transposing the inverse identification `inv p` to the other side: `p ∙ q ＝ r`. Similarly, an identification p ＝ r ∙ inv q` can be proven by transposing the inverse identification `inv q` to the other side: `p ∙ q ＝ r`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  left-transpose-eq-concat :
    {x y : A} (p : x ＝ y) {z : A} (q : y ＝ z) (r : x ＝ z) →
    p ∙ q ＝ r → q ＝ inv p ∙ r
  left-transpose-eq-concat refl q r s = s

  right-transpose-eq-concat :
    {x y : A} (p : x ＝ y) {z : A} (q : y ＝ z) (r : x ＝ z) →
    p ∙ q ＝ r → p ＝ r ∙ inv q
  right-transpose-eq-concat p refl r s = (inv right-unit ∙ s) ∙ inv right-unit
```
