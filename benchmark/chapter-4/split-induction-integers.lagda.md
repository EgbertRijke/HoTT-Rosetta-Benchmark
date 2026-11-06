# The Split Induction Principle of the Integers

```agda
module chapter-4.split-induction-integers where

open import universe-levels
open import chapter-3

open import chapter-4.coproduct-types
open import chapter-4.inclusion-of-negative-integers
open import chapter-4.inclusion-of-positive-integers
open import chapter-4.integers
open import chapter-4.negative-one-integer
open import chapter-4.one-integer
open import chapter-4.zero-integer
```

## Statement

The split induction principle of the integers states that for any type family `P` over `ℤ`, we can define a dependent function `f : Π(k : ℤ) P(k)` by

```text
  f(-1_ℤ)                ≔ p₋₁,
  f(in-neg-ℤ(succ-ℕ(n))) ≔ p_-S(n , f(in-neg-ℤ(n))),
  f(0_ℤ)                 ≔ p₀,
  f(1_ℤ)                 ≔ p₁,
  f(in-pos-ℤ(succ-ℕ(n))) ≔ p_S(n , f(in-pos-ℤ(n))),
```

where the types of `p₋₁`, `p_-S`, `p₀`, `p₁`, and `p_S` have the following types:

```text
  p₋₁ : P(-1_ℤ),
  p_-S : Π(n : ℕ) P(in-neg-ℤ(n)) → P(in-neg-ℤ(succ-ℕ(n))),
  p₀  : P(0_ℤ),
  p₁  : P(1_ℤ),
  p_S  : Π(n : ℕ) P(in-pos-ℤ(n)) → P(in-pos-ℤ(succ-ℕ(n))).
```

## Remark

An induction principle more deserving of the name "integer induction" will be derived in chapter 22.

## Formalization

```agda
ind-ℤ :
  {l : Level} (P : ℤ → UU l) →
  P neg-one-ℤ →
  ((n : ℕ) → P (in-neg-ℤ n) → P (in-neg-ℤ (succ-ℕ n))) →
  P zero-ℤ →
  P one-ℤ →
  ((n : ℕ) → P (in-pos-ℤ n) → P (in-pos-ℤ (succ-ℕ n))) →
  (k : ℤ) → P k
ind-ℤ P p-1 p-S p0 p1 pS (inl zero-ℕ) = p-1
ind-ℤ P p-1 p-S p0 p1 pS (inl (succ-ℕ x)) =
  p-S x (ind-ℤ P p-1 p-S p0 p1 pS (inl x))
ind-ℤ P p-1 p-S p0 p1 pS (inr (inl _)) = p0
ind-ℤ P p-1 p-S p0 p1 pS (inr (inr zero-ℕ)) = p1
ind-ℤ P p-1 p-S p0 p1 pS (inr (inr (succ-ℕ x))) =
  pS x (ind-ℤ P p-1 p-S p0 p1 pS (inr (inr x)))
```
