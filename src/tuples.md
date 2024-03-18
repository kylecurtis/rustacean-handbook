# Tuples

In Rust, a tuple is a fixed-size collection of elements of different types. Tuples are declared using parentheses `()` and can contain a comma-separated list of values.

<br>

---

## Declaring Tuples

To declare a tuple, you can use the following syntax:

```rust
let tuple_name = (value1, value2, ..., valueN);
```

<br>

Here's an example of declaring a tuple with different types of elements:

```rust
let planet = ("Earth", 2024, true);
```

In this example, `planet` is a tuple that contains a string `"Earth"`, an integer `2024`, and a boolean `true`.

<br>

> **NOTE:** Rust infers the tuple type based on the provided values. The type of `planet` is `(&str, i32, bool)`.

<br>

---

## Accessing Tuple Elements

Tuple elements can be accessed using pattern matching or dot notation with the index.

Using pattern matching:

```rust
let planet = ("Earth", 2024, true);
let (name, year, is_habitable) = planet;
println!("Name: {}", name); // Output: Name: Earth
println!("Year: {}", year); // Output: Year: 2024 
println!("Is Habitable: {}", is_habitable); // Output: Is Habitable: true
```

<br>

Using dot notation with the index:

```rust
let planet = ("Earth", 2024, true);
println!("Name: {}", planet.0); // Output: Name: John
println!("Year: {}", planet.1); // Output: Year: 30
println!("Is Habitable: {}", planet.2); // Output: Is Habitable: true
```

<br>

> **NOTE:** The index starts from 0 for the first element and goes up to `N-1` for the last element in a tuple with `N` elements.

<br>

---

## Tuple Destructuring

Tuple destructuring allows you to unpack the elements of a tuple into separate variables:

```rust
let planet = ("Earth", 2024, true);
let (name, year, is_habitable) = planet;
```

In this example, the elements of `planet` are unpacked into the variables `name`, `year`, and `is_habitable`, respectively.

<br>

---

## Empty Tuples

Rust also has a special tuple type called the "unit" or "empty" tuple, represented as `()`. It is used when no value is needed or returned.

```rust
let empty_tuple = ();
```

<br>

> **NOTE:** The unit tuple is commonly used as the return type of functions that don't return any meaningful value.

<br>

---

## Tuple Methods

Tuples in Rust have a few methods available:

- `len()`: Returns the number of elements in the tuple.
- `iter()`: Returns an iterator over the tuple elements.

<br>

Here's an example of using tuple methods:

```rust
let numbers = (1, 2, 3);
println!("Length: {}", numbers.len()); // Output: Length: 3

for num in numbers.iter() {
    println!("{}", num);
}
```

<br>

> **NOTE:** Tuples are useful when you need to group together a fixed number of values of different types. They provide a lightweight way to represent a collection of related values without the need for a custom struct.

