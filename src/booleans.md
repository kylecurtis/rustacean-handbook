# Booleans

The boolean type in Rust is represented by the keyword `bool`. It has two possible values: `true` and `false`. Booleans are used to represent logical values and are commonly used in conditional statements and expressions.

<br>

---

<br>

## Declaring Boolean Variables

To declare a boolean variable, you can use the `bool` type annotation:

```rust
let is_true: bool = true;
let is_false: bool = false;
```

<br>

Alternatively, you can let Rust infer the boolean type based on the assigned value:

```rust
let is_true = true;
let is_false = false;
```

<br>

<br>

---

<br>

## Boolean Operations

Rust supports the following boolean operations:

- Logical AND (`&&`): Returns `true` if both operands are `true`, otherwise returns `false`.

- Logical OR (`||`): Returns `true` if at least one operand is `true`, otherwise returns `false`.

- Logical NOT (`!`): Returns the opposite value of the operand. If the operand is `true`, it returns `false`, and vice versa.

<br>

Here are some examples of boolean operations:

```rust
let a = true;
let b = false;

let result_and = a && b; // false
let result_or = a || b; // true
let result_not = !a; // false
```

<br>

<br>

---

<br>

## Boolean Expressions

Boolean expressions are used to evaluate conditions and make decisions in control flow statements like `if`, `while`, and `loop`.

```rust
let x = 5;

if x > 0 {
    println!("x is positive");
} else {
    println!("x is zero or negative");
}
```

<br>

In this example, the condition `x > 0` is a boolean expression that evaluates to `true` if `x` is greater than zero, and `false` otherwise.

<br>

<br>

---

<br>

## Comparing Values

Rust provides comparison operators to compare values and produce boolean results:

- Equal to (`==`): Returns `true` if the operands are equal, otherwise returns `false`.

- Not equal to (`!=`): Returns `true` if the operands are not equal, otherwise returns `false`.

- Greater than (`>`): Returns `true` if the left operand is greater than the right operand, otherwise returns `false`.

- Less than (`<`): Returns `true` if the left operand is less than the right operand, otherwise returns `false`.

- Greater than or equal to (`>=`): Returns `true` if the left operand is greater than or equal to the right operand, otherwise returns `false`.

- Less than or equal to (`<=`): Returns `true` if the left operand is less than or equal to the right operand, otherwise returns `false`.

<br>

Here are some examples of using comparison operators:

```rust
let a = 5;
let b = 10;

let is_equal = a == b; // false
let is_not_equal = a != b; // true
let is_greater = a > b; // false
let is_less = a < b; // true
let is_greater_equal = a >= b; // false
let is_less_equal = a <= b; // true
```

<br>

> **NOTE:** Boolean values and expressions are fundamental in Rust for making decisions, controlling program flow, and representing logical conditions.
