# The Fibonacci Sequence

```agda
module section-3-3-fibonacci-sequence where
```

## Statement

Define the Fibonacci sequence `F : ℕ → ℕ`.

## Construction

The **Fibonacci sequence** `F : ℕ → ℕ` is defined by

```text
                  F(0) ≔ 0
                  F(1) ≔ 1
  F(succ-ℕ(succ-ℕ(n))) ≔ F(succ-ℕ(n)) + F(n).
```

## Formalization

```agda
fibonacci-ℕ : ℕ → ℕ
fibonacci-ℕ 0 = 0
fibonacci-ℕ (succ-ℕ 0) = 1
fibonacci-ℕ (succ-ℕ (succ-ℕ n)) = fibonacci-ℕ (succ-ℕ n) +ℕ fibonacci-ℕ n
```

