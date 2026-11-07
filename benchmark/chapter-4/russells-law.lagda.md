# Russell's Law

```agda
module chapter-4.russells-law where

open import universe-levels
open import chapter-4.logical-equivalences
open import chapter-4.negation
```

## Statement

**Russell's law** asserts that negation has no fixed points; that is, there is an element of type

```text
  ¬ (A ↔ ¬ A).
```

## Formalization

```agda
russells-law :
  {l : Level} (A : UU l) → ¬ (A ↔ ¬ A)
russells-law A e =
  ( λ (h : ¬ A) → h (backward-implication e h))
  ( λ (a : A) → forward-implication e a a)
```
