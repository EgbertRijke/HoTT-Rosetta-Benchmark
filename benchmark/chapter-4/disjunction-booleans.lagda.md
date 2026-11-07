# Disjunction on the Booleans

```agda
module chapter-4.disjunction-booleans where

open import chapter-4.booleans
```

## Statement

**Boolean disjunction** is a binary function `disjunction-bool : bool → bool → bool` given by

```text
  true  true  ↦ true,
  true  false ↦ true,
  false true  ↦ true,
  false false ↦ false.
```

## Formalization

```agda
disjunction-bool : bool → bool → bool
disjunction-bool true q = true
disjunction-bool false q = q
```

## Remark

In the formalization below we will give a function that evaluates as specified, but its definition uses pattern matching in only one variable.
