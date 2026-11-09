# The Mac Lane Pentagon for the Associator of Identifications

```agda
module chapter-5.mac-lane-pentagon-associator-identifications where

open import universe-levels
open import chapter-5.action-on-identifications-functions
open import chapter-5.associator-concatenation-identifications
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

Consider four consecutive identifications

```text
      p       q       r       s
  a ===== b ===== c ===== d ===== e
```

in a type `A`. Thene there are five identifications

```text
  α₁ : ((p ∙ q) ∙ r) ∙ s ＝ (p ∙ (q ∙ r)) ∙ s
  α₂ : (p ∙ (q ∙ r)) ∙ s ＝ p ∙ ((q ∙ r) ∙ s)
  α₃ : p ∙ ((q ∙ r) ∙ s) ＝ p ∙ (q ∙ (r ∙ s))
  α₄ : ((p ∙ q) ∙ r) ∙ s ＝ (p ∙ q) ∙ (r ∙ s)
  α₅ : (p ∙ q) ∙ (r ∙ s) ＝ p ∙ (q ∙ (r ∙ s))
```

as in in the pentagon

```text
                                  α₄
  ((p ∙ q) ∙ r) ∙ s  ==========================  (p ∙ q) ∙ (r ∙ s)
          ∥                                            ∥ 
       α₁ ∥                                            ∥ α₅
          ∥                                            ∥
  (p ∙ (q ∙ r)) ∙ s ===== p ∙ ((q ∙ r) ∙ s) ===== p ∙ (q ∙ (r ∙ s))
                      α₂                      α₃
```

This pentagon commutes:

```text
  (α₁ ∙ α₂) ∙ α₃ = α₄ ∙ α₅.
```

## Formalization

```agda
module _
  {l : Level} {A : UU l} {x y z w v : A}
  where

  coherence-pentagon-identifications :
    (top : x ＝ y)
    (top-left : x ＝ z) (top-right : y ＝ w)
    (bottom-left : z ＝ v) (bottom-right : w ＝ v) → UU l
  coherence-pentagon-identifications
    top top-left top-right bottom-left bottom-right =
    top-left ∙ bottom-left ＝ (top ∙ top-right) ∙ bottom-right

mac-lane-pentagon :
  {l : Level} {A : UU l} {a b c d e : A}
  (p : a ＝ b) (q : b ＝ c) (r : c ＝ d) (s : d ＝ e) →
  let α₁ = (ap (_∙ s) (assoc p q r))
      α₂ = (assoc p (q ∙ r) s)
      α₃ = (ap (p ∙_) (assoc q r s))
      α₄ = (assoc (p ∙ q) r s)
      α₅ = (assoc p q (r ∙ s))
  in
    coherence-pentagon-identifications α₁ α₄ α₂ α₅ α₃
mac-lane-pentagon refl refl refl refl = refl
```

