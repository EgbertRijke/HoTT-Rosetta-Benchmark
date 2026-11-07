# Double Negation Introduction

```agda
module chapter-4.double-negation-introduction where

open import universe-levels
open import chapter-4.double-negation
```

## Statement

**Double negation introduction** is a function `A → ¬¬ A`.

## Formalization

```agda
intro-double-negation : {l : Level} {A : UU l} → A → ¬¬ A
intro-double-negation a f = f a
```
