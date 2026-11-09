# Composing Transport Along Identifications

```agda
module chapter-5.composing-transport-along-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
open import chapter-5.transport-along-concatenated-identifications
open import chapter-5.transport-along-identifications
```

## Statement

Consider a type family `B` over `A`, identifications `p : x ＝ y` and `q : y ＝ z`, and an element `u : B x`. Then the composition of transport along `q` followed by transport along `p` is transport along `p ∙ q`:

```text
  tr B q (tr P p u) ＝ tr B (p ∙ q) u.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : A → UU l2}
  where

  comp-tr :
    {x y z : A} (p : x ＝ y) (q : y ＝ z) (b : B x) →
    tr B q (tr B p b) ＝ tr B (p ∙ q) b
  comp-tr p q b = inv (tr-concat p q b)
```
