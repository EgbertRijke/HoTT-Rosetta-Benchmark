# Right Unwhiskering With Respect to Concatenation of Identifications

```agda
module chapter-5.right-unwhiskering-concatenation-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.injectivity-based-postconcatenation-identifications
```

## Statement

The **right unwhiskering operation** with respect to concatenation of identifications is a function

```text
  (r : y ＝ z) → (p ∙ r ＝ q ∙ r) → (p ＝ q)
```

for any pair of identifications `p q : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  right-unwhisker-concat :
    {x y z : A} {p q : x ＝ y} → (r : y ＝ z) → p ∙ r ＝ q ∙ r → p ＝ q
  right-unwhisker-concat r = is-injective-concat' r
```
