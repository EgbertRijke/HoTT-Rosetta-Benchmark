# The Involutiveness of Inverting Identifications

```agda
module chapter-5.involutiveness-inverting-identifications where

open import universe-levels
open import chapter-5.concatenation-identifications
open import chapter-5.identity-types
open import chapter-5.inverting-identifications
```

## Statement

Inverting identifications is involutive in the sense that there is an identification

```text
  inv (inv p) ＝ p
```

for any `p : x ＝ y`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  inv-inv : {x y : A} (p : x ＝ y) → inv (inv p) ＝ p
  inv-inv refl = refl
```

