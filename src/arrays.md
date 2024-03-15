# Arrays

In Rust, an array is a fixed-size collection of elements of the same type. Arrays are declared using square brackets `[]` and the size of the array is specified at compile time.

<br>

---

## Declaring Arrays

To declare an array, you can use the following syntax:

```rust
let array_name: [type; size] = [value1, value2, ..., valueN];
```

<br>

Here's an example of declaring an array of integers:

```rust
let numbers: [i32; 5] = [1, 2, 3, 4, 5];
```

> **NOTE:** In this example, `numbers` is an array of type `[i32; 5]`, which means it holds 5 elements of type `i32`.

<br>

You can also let Rust infer the array type based on the provided values:

```rust
let numbers = [1, 2, 3, 4, 5];
```

<br>

<br>

---

### Accessing Array Elements

Array elements can be accessed using indexing. The index starts from 0 for the first element and goes up to `size - 1` for the last element.

```rust
let numbers = [1, 2, 3, 4, 5];
println!("First element: {}", numbers[0]); // Output: First element: 1
println!("Third element: {}", numbers[2]); // Output: Third element: 3
```

<br>

> **NOTE:** Rust performs bounds checking at runtime to ensure that array accesses are within the valid range. Attempting to access an out-of-bounds index will result in a runtime panic.

<br>

<br>

---

## Array Initialization

Rust provides a shorthand syntax to initialize an array with the same value for all elements:

```rust
let array_name = [value; size];
```

<br>

Here's an example of initializing an array with the same value:

```rust
let zeros = [0; 5]; // [0, 0, 0, 0, 0]
let ones = [1; 3]; // [1, 1, 1]
```

<br>

<br>

---

## Array Methods

Arrays in Rust have a few methods available:

- `len()`: Returns the number of elements in the array.
- `is_empty()`: Returns `true` if the array is empty (has zero elements), otherwise returns `false`.
- `iter()`: Returns an iterator over the array elements.

<br>

Here's an example of using array methods:

```rust
let numbers = [1, 2, 3, 4, 5];
println!("Length: {}", numbers.len()); // Output: Length: 5
println!("Is empty? {}", numbers.is_empty()); // Output: Is empty? false

for num in numbers.iter() {
    println!("{}", num);
}
```

<br>

<br>

---


## Arrays and Slices

A slice is a reference to a contiguous sequence of elements in a collection. Arrays can be converted to slices using the `&` operator:

```rust
let numbers = [1, 2, 3, 4, 5];

let slice = &numbers[1..4]; // [2, 3, 4]
println!("{}")
```

In this example, `slice` is a reference to a subarray of `numbers` starting from index 1 (inclusive) up to index 4 (exclusive).

<br>

> **NOTE:** Slices provide a way to work with a portion of an array without copying the elements.
