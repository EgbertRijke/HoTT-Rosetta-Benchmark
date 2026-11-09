# Transport Along Concatenated Identifications

```agda
module chapter-5.transport-along-concatenated-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.transport-along-identifications
```

## Statement

Consider a type family `B` over `A`, identifications `p : x ＝ y` and `q : y ＝ z`, and an element `u : B x`. Then transport along `p ∙ q` is the composition of transport along `q` followed by transport along `p`:

```text
  tr B (p ∙ q) u ＝ tr B q (tr P p u).
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : A → UU l2}
  where

  tr-concat :
    {x y z : A} (p : x ＝ y) (q : y ＝ z) (u : B x) →
    tr B (p ∙ q) u ＝ tr B q (tr B p u)
  tr-concat refl q b = refl
```
