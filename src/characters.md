# Characters

In Rust, the character type is represented by the `char` keyword. It is used to represent a single Unicode character and is stored using 32 bits (4 bytes).

<br>

<br>

---

<br>

## Declaring Characters

To declare a character variable, you can use the `let` keyword followed by the variable name and the `char` type annotation:

```rust
let my_char: char = 'A';
```

<br>

Alternatively, you can let Rust infer the character type based on the assigned value:

```rust
let my_char = 'Ü'; // Uppercase Umlaut (U)
```

<br>

> **NOTE:** Characters are enclosed in single quotes (`''`) to distinguish them from string literals.

<br>

<br>

---

<br>

## Unicode Support

Rust's `char` type supports Unicode, which means it can represent a wide range of characters from various scripts and languages. 

Unicode characters can be written using Unicode code points or escape sequences.

```rust
let unicode_char = '🦀';
let escaped_char = '\u{129408}'; // Unicode escape sequence for '🦀'
```

<br>

> **NOTE:** In the above example, both `unicode_char` and `escaped_char` represent the same Unicode crab character.

<br>

<br>

---

<br>

## Character Escapes

Rust supports character escape sequences to represent special characters or characters that are difficult to type directly:

- `\n`: Newline
- `\r`: Carriage return
- `\t`: Tab
- `\\`: Backslash
- `\'`: Single quote
- `\"`: Double quote

Here are some examples of using character escapes:

```rust
let newline = '\n';
let tab = '\t';
let single_quote = '\'';
let double_quote = '\"';
```

<br>

<br>

---

<br>

## Character Methods

The `char` type in Rust provides several useful methods for working with characters. Some commonly used methods include:

- `is_alphabetic()`: Returns `true` if the character is an alphabetic character.
- `is_digit()`: Returns `true` if the character is a decimal digit.
- `is_lowercase()`: Returns `true` if the character is lowercase.
- `is_uppercase()`: Returns `true` if the character is uppercase.
- `to_lowercase()`: Converts the character to its lowercase equivalent.
- `to_uppercase()`: Converts the character to its uppercase equivalent.

<br>

Here are some examples of using character methods:

```rust
let char_a: char = 'a';
let char_b: char = 'B';
let char_1: char = '1';

println!("Is 'a' alphabetic? {}", char_a.is_alphabetic()); // true
println!("Is 'B' lowercase? {}", char_b.is_lowercase()); // false
println!("Is '1' a digit? {}", char_1.is_numeric()); // true

let uppercase_a = char_a.to_uppercase().next().unwrap();
println!("Uppercase 'a': {}", uppercase_a); // 'A'
```

<br>

> **Note:** Some character methods return an iterator, so you may need to use `next()` and `unwrap()` to get the resulting character.
