+++
Title = "I'm Learning Rust"
+++

### Variable Bindings

the keyword "let" introduces a variable binding

```rust
let x; //declare "x"
x = 42; //assign 42 to "x"
```
or

```rust
let x = 42;
```

specify type explicitly with a type annotation ":"
(this is not necessary to using the variable; can be inferred)

```rust 
let x: i32; //"i32" is a signed 32-bit integer; "u32" for unsigned
x = 42;
```

or 
```rust
let x: i32 = 42;
```

underscore throws values away

```rust
let _ = 42; //does nothing bc 42 is a constant

let _ = get_thing(); //calls the function and throws away its result
```

?? why would you need to throw something away?

if you name a variable something that starts with an underscore, it can get rid of compiler warnings that you haven't used that variable yet 

shadow bindings 

```rust
let x = 13;
let x = x + 3;
//x is now 16
```
?? why is there a special name for this? doesn't seem like a surprise

### Tuples

fixed-length collections of values of _different types_

```rust
let pair = ('a', 17);
pair.0; //this is 'a'
pair.1; //this is 17
```

annotate type with

```rust
let pair: (char, i32) = ('a', 17);
```

assign variables by destructuring tuples

```rust 
let (some_char, some_int) = ('a', 17);
```

can be useful when function returns a tuple

```rust
let (left, right) = slice.split_at(middle);
```

you can throw away part of a tuple

```rust
let (_, right) = slice.split_at(middle);
```

### Statements

statements end at semi-colons, so you can span multiple lines

```rust
let x = vec![1, 2, 3, 4, 5]
    .iter()
    .map(|x| x + 3)
    .fold(0, |x, y| x + y);
```

### Functions

fn declares a function

```rust
fn fair_dice_roll() -> i32 {
    4
    println!("booyah");
} //arrow indicates its return type
```

### Block

brackets declares a block, which has its own scope

```rust
fn main() {
    let x = "out";
    {
        let x = "in"; //this is a different x 
        println!("{}", x);
    }
    println!("{}", x);
}
```

blocks are expressions, so they evaluate to a value

```rust 
let x = 42;
//is equivalent to
let x = { 42 };

let x = {
    let y = 1; 
    let z = 2;
    y + z //evaluation
}; 
```