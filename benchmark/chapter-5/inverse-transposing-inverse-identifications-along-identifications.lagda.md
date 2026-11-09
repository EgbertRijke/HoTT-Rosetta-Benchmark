# Transposing Inverse Identifications along Identifications

```agda
module chapter-5.inverse-transposing-inverse-identifications-along-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.right-unit-law-concatenation-identifications
```

## Statement

An identification `p ∙ q ＝ r` can be proven by transposing the identification `p` to the other side: `q ＝ inv p ∙ r`. Similarly, an identification `p ∙ q ＝ r` can be proven by transposing the identification `q` to the other side: `p ＝ r ∙ inv q`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  inv-left-transpose-eq-concat :
    {x y : A} (p : x ＝ y) {z : A} (q : y ＝ z) (r : x ＝ z) →
    q ＝ inv p ∙ r → p ∙ q ＝ r
  inv-left-transpose-eq-concat refl q r s = s

  inv-right-transpose-eq-concat :
    {x y : A} (p : x ＝ y) {z : A} (q : y ＝ z) (r : x ＝ z) →
    p ＝ r ∙ inv q → p ∙ q ＝ r
  inv-right-transpose-eq-concat p refl r s = right-unit ∙ (s ∙ right-unit)
```
