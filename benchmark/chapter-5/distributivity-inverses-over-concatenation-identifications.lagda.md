# Distributivity of Inverses over Concatenation of Identifications

```agda
module chapter-5.distributivity-inverses-over-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
```

## Statement

The operation of inverting identifications distributes over
concatenation, in the sense that there is an identification

```text
  distributive-inv-concat(p,q) : inv (p ∙ q) = inv q ∙ inv p.
```

for any `p : x = y` and `q : y = z`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  distributive-inv-concat :
    {x y : A} (p : x ＝ y) {z : A} (q : y ＝ z) →
    inv (p ∙ q) ＝ inv q ∙ inv p
  distributive-inv-concat refl refl = refl
```
