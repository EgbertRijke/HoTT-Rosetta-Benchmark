# The Induction Principle for Lists

```agda
module chapter-4.induction-lists where

open import universe-levels
open import chapter-4.lists
```

## Statement

The induction principle for lists asserts that for any type family `P : list A → 𝒰`, if we have

```text
   Pnil : P nil,
  Pcons : (a : A) (l : list A) → P l → P (cons a l),
```

then there is a dependent function `(x : list A) → P x`.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} (P : list A → UU l2)
  where

  ind-list :
    P nil → ((a : A) (as : list A) → P as → P (cons a as)) →
    (x : list A) → P x
  ind-list Pnil Pcons nil = Pnil
  ind-list Pnil Pcons (cons a as) = Pcons a as (ind-list Pnil Pcons as)
```
