# Floating Point Numbers

Rust provides two floating-point types: `f32` and `f64`, which represent single-precision (32-bit) and double-precision (64-bit) floating-point numbers, respectively. These types follow the IEEE 754 standard for floating-point arithmetic.

<br>

<br>

---

<br>

## Floating-Point Literals


In Rust, you can specify the type of a floating-point number using either the type annotation `: f32` or `: f64`, or by appending the suffix `f32` or `f64` to the literal value. 

<br>

> **NOTE:** The default type for floating-point literals is `f64`.

<br>

**Using Type Annotations:**

When declaring a variable or specifying a function parameter or return type, you can use the type annotation `: f32` or `: f64` to explicitly specify the desired floating-point type.

```rust
let x: f32 = 3.14;
let y: f64 = 2.71828;
```

<br>

In the above example, `x` is explicitly declared as an `f32` type, and `y` is declared as an `f64` type using type annotations.

<br>

**Using Suffixes:**

Alternatively, you can append the suffix `f32` or `f64` to the literal value to specify the desired floating-point type.

```rust
let x = 3.14f32; // f32
let y = 2.71828f64; // f64
```

```rust
let area = 10.0f32 * 5.0f32;
```

<br>

In these examples, `x` is specified as an `f32` value using the `f32` suffix, and `y` is specified as an `f64` value using the `f64` suffix. The `area` calculation is performed using `f32` values.

<br>

<br>

---

<br>

## Precision and Rounding

Floating-point numbers have limited precision due to their fixed-size representation. As a result, not all real numbers can be represented exactly, and rounding errors can occur.

```rust
let x: f32 = 0.1 + 0.2;
println!("{}", x); // Output: 0.30000000000000004
```

<br>

In the example above, the result is not exactly 0.3 due to the limitations of floating-point representation.

<br>

When comparing floating-point numbers, it's recommended to use approximate equality comparisons with a small tolerance value (epsilon) to account for potential rounding errors.

```rust
let epsilon = 1e-6; // equivalent to 0.000001 or 0.0001%.
let x: f32 = 0.1 + 0.2;
let y: f32 = 0.3;

if (x - y).abs() < epsilon {
    println!("x and y are approximately equal");
}
```

<br>

<br>

---

<br>

## Special Values

The IEEE 754 standard defines several special values for floating-point numbers:

- Positive and Negative Infinity: Represents values that are too large to be represented.

- NaN (Not a Number): Represents the result of undefined or invalid operations, such as taking the square root of a negative number.

<br>

```rust
let x: f32 = 1.0 / 0.0; // Positive Infinity
```

```rust
let y: f32 = -1.0 / 0.0; // Negative Infinity
```

```rust
let z: f32 = f32::NAN; // NaN
```

<br>

<br>

---

<br>

## Floating-Point Operations

Rust provides various arithmetic operations and mathematical functions for floating-point numbers:

```rust
let x: f32 = 2.5;
let y: f32 = 1.7;

let sum = x + y;
let diff = x - y;
let prod = x * y;
let quot = x / y;

let sqrt = f32::sqrt(x);
let abs = f32::abs(-3.14);
```

It's important to be aware of the potential for rounding errors and precision loss when performing floating-point operations.

<br>

> **NOTE:** When performing arithmetic operations or comparisons between floating-point numbers, the types must match. If you mix `f32` and `f64` values in an operation, you'll need to explicitly convert one of the types to match the other.

<br>

**Explicit Conversion**

```rust
let x: f32 = 3.14;
let y: f64 = 2.71828;

// Explicit conversion from f64 to f32
let result = x + y as f32;
```

In this example, `y` is explicitly converted from `f64` to `f32` using the `as` keyword to match the type of `x` before performing the addition.

