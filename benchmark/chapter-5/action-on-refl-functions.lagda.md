# The Action on Refl of Functions

```agda
module chapter-5.action-on-refl-functions where

open import universe-levels
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

The action on identifications of a function `f : A → B` on the `refl` identification is given by

```text
  ap f refl ＝ refl.
```

This identification follows directly from the definition of `ap f` by pattern matching.

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (f : A → B) (x : A)
  where

  ap-refl : ap f (refl {x = x}) ＝ refl
  ap-refl = refl
```
