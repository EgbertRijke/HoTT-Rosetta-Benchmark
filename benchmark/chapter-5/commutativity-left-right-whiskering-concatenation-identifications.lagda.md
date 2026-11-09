### Commutativity of left and right whiskering of identifications

```agda
module chapter-5.commutativity-left-right-whiskering-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.left-whiskering-concatenation-identifications
open import chapter-5.right-unit-law-concatenation-identifications
open import chapter-5.right-whiskering-concatenation-identifications
```

## Statement

Consider two identifications `α : p ＝ p'` and `β : q ＝ q'`, where
`p p' : x ＝ y` and `q q' : y ＝ z`. Then the square

```text
                            right-whisker-concat α q
                        p ∙ q ------------------> p' ∙ q
                          |                          |
  left-whisker-concat p β |                          | left-whisker-concat p' β
                          |                          |
                          ∨                          ∨
                        p ∙ q' -----------------> p' ∙ q'
                            right-whisker-concat α q'
```

commutes. We give a direct proof that this square commutes, a direct square that the transposed square commutes, and then we show that the second commutativity proof is the inverse of the first commutativity proof.

## Formalization

```agda
module _
  {l : Level} {A : UU l} {x y z : A} {p p' : x ＝ y} {q q' : y ＝ z}
  where

  commutative-left-whisker-right-whisker-concat :
    (β : q ＝ q') (α : p ＝ p') →
    left-whisker-concat p β ∙ right-whisker-concat α q' ＝
    right-whisker-concat α q ∙ left-whisker-concat p' β
  commutative-left-whisker-right-whisker-concat β refl =
    right-unit

  commutative-right-whisker-left-whisker-concat :
    (α : p ＝ p') (β : q ＝ q') →
    right-whisker-concat α q ∙ left-whisker-concat p' β ＝
    left-whisker-concat p β ∙ right-whisker-concat α q'
  commutative-right-whisker-left-whisker-concat α refl =
    right-unit

  compute-inv-commutative-right-whisker-left-whisker-concat :
    (β : q ＝ q') (α : p ＝ p') →
    ( inv (commutative-right-whisker-left-whisker-concat α β)) ＝
    ( commutative-left-whisker-right-whisker-concat β α)
  compute-inv-commutative-right-whisker-left-whisker-concat refl refl =
    refl
```
