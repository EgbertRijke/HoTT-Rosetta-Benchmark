# Equational Reasoning

```agda
module chapter-5.equational-reasoning where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
```

## Statement

**Equational reasoning** is reasoning by chaining identifications together. For example, the following chain of logical equivalences

```text
  A ＝ B
    ＝ C
    ＝ D
```

shows that `A ＝ D`.

## Formalization

```agda
infixl 1 equational-reasoning_
infixl 0 step-equational-reasoning

equational-reasoning_ :
  {l : Level} {X : UU l} (x : X) → x ＝ x
equational-reasoning x = refl

step-equational-reasoning :
  {l : Level} {X : UU l} {x y : X} →
  (x ＝ y) → (u : X) → (y ＝ u) → (x ＝ u)
step-equational-reasoning p z q = p ∙ q

syntax step-equational-reasoning p z q = p ＝ z by q
```
