# Irrefutability of the Gödel­Dummett axiom

```agda
module chapter-4.irrefutability-of-godel-dummett where

open import universe-levels
open import chapter-4.coproduct-types
open import chapter-4.double-negation
open import chapter-4.ex-falso
open import chapter-4.functoriality-negation
open import chapter-4.negation
```

## Statement

The Gödel­Dummett axiom, which asserts that there is an element of type `(A → B) + (B → A)`, is irrefutable in the sense that there is an element of type

```text
  ¬¬ ((A → B) + (B → A)).
```

## Formalization

```agda
module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2}
  where

  is-irrefutable-gödel-dummett-axiom :
    ¬¬ ((A → B) + (B → A))
  is-irrefutable-gödel-dummett-axiom f =
    ( λ na → map-neg inl f (λ a → ex-falso (na a)))
    ( λ a → map-neg inr f (λ _ → a))
```
