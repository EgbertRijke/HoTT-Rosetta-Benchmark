# Constant Maps

```agda
module exercise-2-3-constant-maps where

open import universe-levels
```

## Statement

Construct for each `b : B` the **constant map** `const b : A → B`.

## Formalization

```agda
const : {l1 l2 : Level} (A : UU l1) {B : UU l2} → B → A → B
const A b x = b
```

