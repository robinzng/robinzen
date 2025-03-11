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

if you name a variable something that starts with an underscore, it can get rid of compiler warnings that you haven't used that variable yet 

shadow bindings 

```rust
let x = 13;
let x = x + 3;
// x is now 16
```