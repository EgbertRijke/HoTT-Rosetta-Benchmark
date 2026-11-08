# Concatenation of Identifications

```agda
module chapter-5.concatenation-identifications where

open import universe-levels
open import chapter-5.identity-types
```

## Statement

Let `A` be a type. The **concatenation** operation on identifications is an operation of type

```text
  concat : (x y z : A) → x = y → y = z → x = z
```

given by `concat refl p ≔ p`.

## Formalization

```agda
module _
  {l : Level} {A : UU l}
  where

  infixl 15 _∙_

  _∙_ : {x y z : A} → x ＝ y → y ＝ z → x ＝ z
  refl ∙ q = q
```
