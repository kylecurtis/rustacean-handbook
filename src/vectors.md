# Vectors

In Rust, a vector is a growable, heap-allocated collection of elements of the same type. Vectors are represented by the `Vec<T>` type, where `T` is the type of elements stored in the vector.

<br>

---

## Creating Vectors

To create a new vector, you can use the `Vec::new()` method:

```rust
let mut numbers = Vec::new();
```

<br>

or the `vec!` macro:

```rust
let mut numbers: Vec<i32> = vec![1, 2, 3, 4, 5];
```

<br>

In the first example, `numbers` is an empty vector called `numbers`. In the second example, `numbers` is initialized with the provided type and values using the `vec!` macro.

<br>

---

## Adding Elements

You can add elements to a vector using the `push()` method:

```rust
let mut numbers: Vec<i32> = vec![1, 2, 3];
numbers.push(4);
numbers.push(5);
```

<br>

The `numbers` vector will now contain `[1, 2, 3, 4, 5]`.

<br>

---

## Accessing Elements

Elements in a vector can be accessed using indexing:

```rust
let numbers: Vec<i32> = vec![1, 2, 3, 4, 5];
println!("First element: {}", numbers[0]);
println!("Third element: {}", numbers[2]);
```

<br>

> **NOTE:** Rust performs bounds checking at runtime to ensure that vector accesses are within the valid range. Attempting to access an out-of-bounds index will result in a runtime panic.

<br>

You can also use the `get()` method to safely access elements without causing a panic:

```rust
let numbers: Vec<i32> = vec![1, 2, 3, 4, 5];
match numbers.get(2) {
    Some(value) => println!("Third element: {}", value),
    None => println!("Index out of bounds"),
}
```

<br>

---

## Updating Elements

You can update elements in a vector by assigning a new value to a specific index:

```rust
let mut numbers = vec![1, 2, 3, 4, 5];
numbers[2] = 10;
println!("Updated vector: {:?}", numbers);
```

The `numbers` vector will now contain `[1, 2, 10, 4, 5]`.

<br>

---

## Vector Methods

Vectors in Rust provide various methods for manipulating and working with the elements:

- `len()`: Returns the number of elements in the vector.
- `capacity()`: Returns the current capacity of the vector (number of elements it can hold without reallocation).
- `is_empty()`: Returns `true` if the vector is empty, `false` otherwise.
- `clear()`: Removes all elements from the vector.
- `pop()`: Removes and returns the last element from the vector, if any.
- `iter()`: Returns an iterator over the vector elements.

<br>

Here's an example of using vector methods:

```rust
let mut numbers = vec![1, 2, 3, 4, 5];
println!("Length: {}", numbers.len());
println!("Capacity: {}", numbers.capacity());
println!("Is empty? {}", numbers.is_empty());

numbers.clear();
println!("After clear, length: {}", numbers.len());

numbers.push(10);
numbers.push(20);
println!("Last element: {:?}", numbers.pop());
```

<br>

---

## Iterating over Vectors

You can iterate over the elements of a vector using a `for` loop:

```rust
let numbers = vec![1, 2, 3, 4, 5];
for num in numbers.iter() {
    println!("{}", num);
}
```

<br>

This will print each element of the `numbers` vector on a separate line.

Vectors are a dynamic and versatile collection type in Rust. They offer flexibility in terms of size and provide convenient methods for working with their elements.

