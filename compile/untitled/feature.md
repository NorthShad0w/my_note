# feature

```
let guess: u32 = guess.trim().parse().expect("Please type a number!");

```

Switching from an `expect` call to a `match` expression is one way of moving from crashing on an error to handling the error.

```
let guess: u32 = match guess.trim().parse() {
    Ok(num) => num,
    Err(_) => continue,
};
```

let     let mut     const

Number literals can also use `_` as a visual separator to make the number easier to read, such as `1_000`, which will have the same value as if you had specified `1000`.



```
fn main() {
    let x: (i32, f64, u8) = (500, 6.4, 1);

    let five_hundred = x.0;

    let six_point_four = x.1;

    let one = x.2;
}
```

Arrays in Rust are different from arrays in some other languages because arrays in Rust have a fixed length

let a: \[i32; 5] = \[1, 2, 3, 4, 5];

Pushing to the stack is faster than allocating on the heap because the allocator never has to search for a place to store new data
