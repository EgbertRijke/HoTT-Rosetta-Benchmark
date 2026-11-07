# The Induction Principle of the Booleans

```agda
module chapter-4.induction-booleans where

open import universe-levels
open import chapter-4.booleans
```

## Statement

The induction principle of the booleans asserts that for any family of types `P(x)` indexed by `x : bool`, there is a ternary function

```text
  ind-bool : P(false) → P(true) → Π(x : bool) P(x)
```

for which the computation rules

```text
  ind-bool(p₀, p₁, false) ≐ p₀
  ind-bool(p₀, p₁, true) ≐ p₁
```

hold.

## Formalization

```agda
ind-bool : {l : Level} (P : bool → UU l) → P true → P false → (b : bool) → P b
ind-bool P p₁ p₀ true = p₁
ind-bool P p₁ p₀ false = p₀
```
