# Reflexivity of Dependent Identifications

```agda
module chapter-5.reflexivity-dependent-identifications where

open import universe-levels
open import chapter-5.dependent-identifications
open import chapter-5.identity-types
```

## Statement

Let `B` be a type family over `A`. The reflexivity dependent identification on `u : B x` over `refl : x ＝ x` is defined to be `refl`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2)
  where

  refl-dependent-identification :
    {x : A} {y : B x} → dependent-identification B refl y y
  refl-dependent-identification = refl
```
