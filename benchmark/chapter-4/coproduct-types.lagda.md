# Coproduct Types

```agda
module chapter-4.coproduct-types where

open import universe-levels
```

## Statement

Let `A` and `B` be types. We define the **coproduct** `A + B` to be a type that comes equipped with

```text
  inl : A → A + B
  inr : B → A + B,
```

satisfying the induction principle that for any family of types `P(x)` indexed by `x : A + B`, there is a term

```text
  ind-coprod : (Π(x : A) P(inl(x))) → ((Π(y : B) P(inr(y))) → Π(z : A + B) P(z))
```

for which the computation rules

```text
  ind-coprod(f,g,inl(x)) ≐ f(x)
  ind-coprod(f,g,inr(y)) ≐ g(y)
```

hold. Alternatively, a definition of a dependent function `h : Π(x : A + B) P(x)` by induction using `f : Π(x : A) P(inl(x))` and `g : Π(y : B) P(inr(y))` can be presented by pattern matching as

```text
  h(inl(x)) ≔ f(x)
  h(inr(y)) ≔ g(y).
```

## Formalization

```agda
infixr 10 _+_

data _+_ {l1 l2 : Level} (A : UU l1) (B : UU l2) : UU (l1 ⊔ l2)
  where
  inl : A → A + B
  inr : B → A + B

ind-coproduct :
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} (C : A + B → UU l3) →
  ((x : A) → C (inl x)) → ((y : B) → C (inr y)) →
  (t : A + B) → C t
ind-coproduct C f g (inl x) = f x
ind-coproduct C f g (inr x) = g x

rec-coproduct :
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {C : UU l3} →
  (A → C) → (B → C) → (A + B) → C
rec-coproduct {C = C} = ind-coproduct (λ _ → C)
```

