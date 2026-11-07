# Negation on the Booleans

```agda
module chapter-4.negation-booleans where

open import chapter-4.booleans
```

## Statement

**Boolean negation** is a function `neg-bool : bool → bool` given by

```text
   true ↦ false,
  false ↦ true.
```

## Formalization

```agda
neg-bool : bool → bool
neg-bool true = false
neg-bool false = true
```

