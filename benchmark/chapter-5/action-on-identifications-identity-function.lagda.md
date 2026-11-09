# The Action on Identifications of the Identity Function

```agda
module chapter-5.action-on-identifications-identity-function where

open import universe-levels
open import chapter-2
open import chapter-5.action-on-identifications-functions
open import chapter-5.identity-types
```

## Statement

The identity function `id : A → A` acts on identifications as the identity function, in the sense that there are identifications

```text
  ap id p ＝ p
```

for every `p : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l} {x y : A}
  where

  ap-id : (p : x ＝ y) → ap id p ＝ p
  ap-id refl = refl
```
