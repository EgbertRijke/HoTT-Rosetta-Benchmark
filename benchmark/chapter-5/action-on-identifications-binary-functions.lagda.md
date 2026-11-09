# The Action on Identifications of Binary Functions

```agda
module chapter-5.action-on-identifications-binary-functions where

open import universe-levels
open import chapter-5.action-on-identifications-functions
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

The action on identifications of a binary function `f : A → B → C` is a binary function

```text
  ap-binary f : (x ＝ x') → (y ＝ y') → (f x y ＝ f x' y')
```

satisfying the judgmental equality `ap-binary f refl refl ≐ refl`. However, for better computational behavior, we define `ap-binary f` as:

```text
  ap-binary f p q ＝ ap (f _ y) p ∙ ap (f x' _) q.
```

This definition also satisfies the stated judgmental equality, but has the advantage that it always computes to this specific concatenation of identifications.

## Formalization

```agda
module _
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {C : UU l3} (f : A → B → C)
  where

  ap-binary :
    {x x' : A} (p : x ＝ x') {y y' : B} (q : y ＝ y') → f x y ＝ f x' y'
  ap-binary {x} {x'} p {y} {y'} q = ap (λ r → f r y) p ∙ ap (f x') q
```

