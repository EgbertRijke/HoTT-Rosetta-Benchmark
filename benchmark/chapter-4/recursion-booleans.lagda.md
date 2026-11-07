# The Recursion Principle of the Booleans

```agda
module chapter-4.recursion-booleans where

open import universe-levels
open import chapter-4.booleans
```

## Statement

The recursion principle of the booleans asserts that for any type `A` there is a ternary function

```text
  rec-bool : A → A → bool → A
```

for which the computation rules

```text
  rec-bool(a₀, a₁, false) ≐ a₀
  rec-bool(a₀, a₁, true) ≐ a₁
```

hold.

## Formalization

```agda
rec-bool : {l : Level} {A : UU l} → A → A → bool → A
rec-bool a₁ a₀ true = a₁
rec-bool a₁ a₀ false = a₀
```
