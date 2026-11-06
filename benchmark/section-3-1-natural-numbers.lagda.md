# The type of natural numbers

```agda
module section-3-1-natural-numbers where

open import universe-levels
```

## Statement

The type `ℕ` is formed by the ℕ-**formation** rule

```text

  ---------- ℕ form 
   ⊢ ℕ type 
```

In other words, `ℕ` is postulated to be a type in the empty context.
The introduction rules for `ℕ` equip it with the **zero element** and the **successor function**.

```text

  -----------
   ⊢ 0 : ℕ 
```

```text

  ------------------
   ⊢ succ-ℕ : ℕ → ℕ
```

The type theoretical induction principle of `ℕ` is formulated using a type family `P` over `ℕ`:

```text
   Γ, n : ℕ ⊢ P(n) type
   Γ ⊢ p₀ : P(0)
   Γ ⊢ p_S : Π(n : ℕ) P(n) → P(succ-ℕ(n))
  ---------------------------------------- ℕ-ind
   Γ ⊢ ind-ℕ(p₀, p_S) : Π(n : ℕ) P(n)
```

The computation rule for the base case is

```text
   Γ, n : ℕ ⊢ P(n) type
   Γ ⊢ p₀ : P(0)
   Γ ⊢ p_S : Π(n : ℕ) P(n) → P(succ-ℕ(n))
  ----------------------------------------
   Γ ⊢ ind-ℕ(p₀, p_S,0) ≐ p₀ : P(0).
```

The computation rule for the inductive step has the same premises as the computation rule for the base case:

```text
   Γ, n : ℕ ⊢ P(n) type
   Γ ⊢ p₀ : P(0)
   Γ ⊢ p_S : Π(n : ℕ) P(n) → P(succ-ℕ(n))
  ----------------------------------------------------------------------------------
   Γ, n : ℕ ⊢ ind-ℕ(p₀, p_S, succ-ℕ(n)) ≐ p_S(n, ind-ℕ(p₀, p_S, n)) : P(succ-ℕ(n)).
```

## Formalization

```agda
data ℕ : UU lzero where
  zero-ℕ : ℕ
  succ-ℕ : ℕ → ℕ

{-# BUILTIN NATURAL ℕ #-}
```


