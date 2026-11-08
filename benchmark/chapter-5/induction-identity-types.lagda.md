# The Induction Principle of Identity Types

```agda
module chapter-5.induction-identity-types where

open import universe-levels
open import chapter-5.identity-types
```

## Statement

The induction principle for identity types states that for any family `B : (x : A) → a ＝ x → 𝒰` there is a function

```text
  B a refl → (x : A) (p : a ＝ x) → B x p.
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} (a : A) (B : (x : A) (p : a ＝ x) → UU l2)
  where

  ind-Id : B a refl → (x : A) (p : a ＝ x) → B x p
  ind-Id b x refl = b
```
