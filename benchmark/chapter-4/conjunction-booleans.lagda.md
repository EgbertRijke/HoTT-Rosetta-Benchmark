# Conjunction on the Booleans

```agda
module chapter-4.conjunction-booleans where

open import chapter-4.booleans
```

## Statement

**Boolean conjunction** is a binary function `conjunction-bool : bool → bool → bool` given by

```text
  true  true  ↦ true,
  true  false ↦ false,
  false true  ↦ false,
  false false ↦ false.
```

## Remark

In the formalization below we will give a function that evaluates as specified, but its definition uses pattern matching in only one variable.

## Formalization

```agda
conjunction-bool : bool → bool → bool
conjunction-bool true q = q
conjunction-bool false q = false
```

