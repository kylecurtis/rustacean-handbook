# Integer Types

Rust provides several integer types with different sizes and ranges. These types are signed (can represent both positive and negative numbers) and unsigned (can only represent non-negative numbers).

<br>

---

<br>

## Integer Literals

Integer literals can be written in various formats:

```rust
let decimal = 42; // Decimal literal
```

```rust
let hex = 0xff; // Hexadecimal literal
```

```rust
let octal = 0o77; // Octal literal
```

```rust
let binary = 0b1010; // Binary literal
```

```rust
let byte = b'A'; // Byte literal (u8 only)
```

<br>

You can also use underscores (`_`) as separators to improve readability for larger numbers (seperators are ignored by the Rust compiler):

```rust
let million = 1_000_000;

println!("{}", million)
```

<br>

<br>

---

<br>

## Signed Integer Table

| Type    | Bit-size | Minimum Formula | Maximum Formula | Minimum Value (::MIN) | Maximum Value (::MAX) |
|---------|----------|-----------------|-----------------|----------------------|----------------------|
| `i8`    | 8        | -2^7            | 2^7 - 1         | `i8::MIN`            | `i8::MAX`            |
| `i16`   | 16       | -2^15           | 2^15 - 1        | `i16::MIN`           | `i16::MAX`           |
| `i32`   | 32       | -2^31           | 2^31 - 1        | `i32::MIN`           | `i32::MAX`           |
| `i64`   | 64       | -2^63           | 2^63 - 1        | `i64::MIN`           | `i64::MAX`           |
| `i128`  | 128      | -2^127          | 2^127 - 1       | `i128::MIN`          | `i128::MAX`          |
| `isize` | arch-dependent | -2^(n-1) | 2^(n-1) - 1     | `isize::MIN`         | `isize::MAX`         |

<br>

<br>

---

<br>

## Signed Min & Max Integers

<br>

`i8`: 8-bit signed integer

    min: -128

    max: 127 

<br>

`i16`: 16-bit signed integer

    min: -32_768

    max: 32_767

<br>

`i32`: 32-bit signed integer

    min: -2_147_483_648

    max: 2_147_483_647

<br>

`i64`: 64-bit signed integer

    min: -9_223_372_036_854_775_808

    max: 9_223_372_036_854_775_807

<br>

`i128`: 128-bit signed integer

    min: -170_141_183_460_469_231_731_687_303_715_884_105_728

    max: 170_141_183_460_469_231_731_687_303_715_884_105_727

<br>

<br>

---

<br>

## Signed Integer (Code Examples)

<br>

**i8**

```rust
let num_8: i8 = 127;

println!("{}", num_8);
```

<br>

**i16**

```rust
let num_16: i16 = 32_767;

println!("{}", num_16);
```

<br>

**i32**

```rust
let num_32: i32 = 2_147_483_647;

println!("{}", num_32);
```

<br>

**i64**

```rust
let num_64: i64 = 9_223_372_036_854_775_807;

println!("{}", num_64);
```

<br>

**i128**

```rust
let num_128: i128 = 170_141_183_460_469_231_731_687_303_715_884_105_727;

println!("{}", num_128);
```

<br>

<br>

---

<br>


## Unsigned Integer Table

| Type    | Bit-size | Minimum Formula | Maximum Formula | Minimum Value (::MIN) | Maximum Value (::MAX) |
|---------|----------|-----------------|-----------------|----------------------|----------------------|
| `u8`    | 8        | 0               | 2^8 - 1         | `u8::MIN`            | `u8::MAX`            |
| `u16`   | 16       | 0               | 2^16 - 1        | `u16::MIN`           | `u16::MAX`           |
| `u32`   | 32       | 0               | 2^32 - 1        | `u32::MIN`           | `u32::MAX`           |
| `u64`   | 64       | 0               | 2^64 - 1        | `u64::MIN`           | `u64::MAX`           |
| `u128`  | 128      | 0               | 2^128 - 1       | `u128::MIN`          | `u128::MAX`          |
| `usize` | arch-dependent | 0         | 2^n - 1         | `usize::MIN`         | `usize::MAX`         |

<br>

<br>

---

<br>

## Unsigned Min & Max Integers

<br>

`u8`: 8-bit unsigned integer

    min: 0 

    max: 255

<br>

`u16`: 16-bit unsigned integer

    min: 0

    max: 65_535

<br>

`u32`: 32-bit unsigned integer

    min: 0

    max: 4_294_967_295

<br>

`u64`: 64-bit unsigned integer

    min: 0

    max: 18_446_744_073_709_551_615

<br>

`u128`: 128-bit unsigned integer

    min: 0

    max:  340_282_366_920_938_463_463_374_607_431_768_211_455

<br>

<br>



<br>

---

<br>


## Unsigned Integer (Code Examples)

<br>

**u8**

```rust
let num_u8: u8 = 255;

println!("{}", num_u8);
```

<br>

**u16**

```rust
let num_u16: u16 = 65_535;

println!("{}", num_u16);
```

<br>

**u32**

```rust
let num_u32: u32 = 4_294_967_295;

println!("{}", num_u32);
```

<br>

**u64**

```rust
let num_u64: u64 = 18_446_744_073_709_551_615;

println!("{}", num_u64);
```

<br>

**u128**

```rust
let num_u128: u128 = 340_282_366_920_938_463_463_374_607_431_768_211_455;

println!("{}", num_u128);
```

<br>

<br>

---

<br>



### Integer Overflow

Rust provides two modes for handling integer overflow: wrapping and panic.

In debug mode (default), Rust checks for integer overflow at runtime and panics if overflow occurs:

```rust
let x: u8 = 255;
let y = x + 1; // Panics: thread 'main' panicked at 'attempt to add with overflow'
```

<br>

In release mode (with optimizations enabled), Rust uses two's complement wrapping arithmetic, where the value wraps around to the minimum value if overflow occurs. 

***NOTE***: This will not work as expected if you try running here! You must run this code by compiling in release mode.

```rust
let x: u8 = 255;
let y = x + 1; // y = 0 (wrapped around)
```

<br>

You can explicitly wrap on overflow using the wrapping methods provided by integer types:

***NOTE***: This will also not work as expected if you try running here!

```rust
let x: u8 = 255;
let y = x.wrapping_add(1); // y = 0
```

<br>

---

<br>

### Integer Methods and Constants

Integer types in Rust provide various methods and associated constants for common operations and properties. Some examples include:

```rust
// Min & Max
println!("Minimum value: {}", i32::MIN);
println!("Maximum value: {}", i32::MAX);
```

<br>

```rust
// Bit size
println!("Number of bits: {}", i32::BITS); // 32
```

<br>

```rust
// Check if number is positive (returns boolean)
let x: i32 = 42;
println!("Is positive: {}", x.is_positive()); // true
```

<br>

```rust
// Absolute value
let y: i32 = 42;
println!("Absolute value: {}", y.abs()); // 42
```

<br>

<br>

---

<br>

### Casting Between Integer Types

You can cast between integer types using the `as` keyword:

```rust
let x: i32 = 42;
let y: u8 = x as u8; // y = 42
```

<br>

Be cautious when casting between types, as it may lead to loss of precision or unexpected behavior if the target type cannot represent the original value.

<br>
