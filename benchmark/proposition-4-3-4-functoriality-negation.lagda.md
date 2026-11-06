# Functoriality of Negation

```agda
module proposition-4-3-4-functoriality-negation where

open import universe-levels
open import definition-4-3-2-negation
```

## Statement

For any two types `P` and `Q`, there is a function
  
```text
  (P → Q) → (¬ Q → ¬ P).
```

## Proof

The desired function is defined by `λ`-abstraction, so we begin by assuming that we have a function `f : P → Q`.
Then we have to construct a function `¬ Q → ¬ P`, which is again constructed by `λ`-abstraction.
We assume that we have `q̃ : ¬ Q`.
By our definition of `¬ Q` we see that `q̃` is a function `Q → ∅`.
Now we have to construct a term of type `¬ P`, which is the type of functions `P → ∅`.
We apply `λ`-abstraction once more, so we assume `p : P`.
Now we have

```text
  f : P → Q
  q̃ : Q → ∅
  p : P,
```

and our goal is to construct a term of the empty type.

Since we have `f : P → Q` and `p : P`, we obtain `f(p) : Q`.
Moreover, we have `q̃ : Q → ∅`, so we obtain `q̃(f(p)) : ∅`.
This completes the proof.
The function we have constructed is
  
```text
  λ f. λ q̃. λ p. q̃(f(p)) : (P → Q) → (¬ Q → ¬ P). □
```

## Formalization

```agda
map-neg : {l1 l2 : Level} {P : UU l1} {Q : UU l2} → (P → Q) → (¬ Q → ¬ P)
map-neg f nq p = nq (f p)
```

