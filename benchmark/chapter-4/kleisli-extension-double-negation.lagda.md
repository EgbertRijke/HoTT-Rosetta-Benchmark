# The Kleisli Extension for Double Negation

```agda
module chapter-4.kleisli-extension-double-negation where

open import universe-levels
open import chapter-4.double-negation
```

## Statement

The **Kleisli extension** for double negation is a map

```text
  (A → ¬¬ B) → (¬¬ A → ¬¬ B).
```

## Formalization

```agda
extend-double-negation :
  {l1 l2 : Level} {P : UU l1} {Q : UU l2} →
  (P → ¬¬ Q) → (¬¬ P → ¬¬ Q)
extend-double-negation {P = P} {Q = Q} f nnp nq = nnp (λ p → f p nq)
```
