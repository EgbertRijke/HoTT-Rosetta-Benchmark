# Substitution Law for Transport Along Identifications

```agda
module chapter-5.substitution-law-for-transport-along-identifications where

open import universe-levels
open import chapter-2
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
open import chapter-5.transport-along-action-on-identifications-functions
open import chapter-5.transport-along-identifications
```

## Statement

Consider a type family `B : A → UU l3` and a map `f : X → A`. Then transport along `ap f p` in `B` is the same as transport along `p` in `B ∘ f`. This law is a special case of the rule for transport along the action on identifications of a function.

## Formalization

```agda
module _
  {l1 l2 l3 : Level} {X : UU l1} {A : UU l2} (B : A → UU l3) (f : X → A)
  where

  substitution-law-tr :
    {x y : X} (p : x ＝ y) {u : B (f x)} →
    tr B (ap f p) u ＝ tr (B ∘ f) p u
  substitution-law-tr p {x'} = tr-ap f (λ _ → id) p x'
```
