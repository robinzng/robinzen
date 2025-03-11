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
fn fair_dice_roll() -> i32 {//arrow indicates its return type
    4 //omitting the semicolon is equivalent to returning
} 
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

if conditions are expressions

```rust
fn fair_dice_roll() -> i32 {
    if feeling_lucky {
        6
    } else {
        4
    }
}
```

match is also an expression
??? what is a match
??? what are the columns for? 

```rust 
fn fair_dice_roll() -> i32 {
    match feeling_lucky {
        true => 6,
        false => 4, 
    }
}
```

### Field access + method calling

dots are used to access fields of a value or call a method on a value

```rust
let a = (10, 20);
a.0; //this is 10

let b = "booyah";
b.len(); //this is 6
```

### Modules and use syntax? 

double colons access fields in namespaces

```rust
let least = std::cmp::min(3, 8); //this is 3
//std is a crate/library, cmp is a module/source file, min is a function
```

"use" directives can bring in names from other namespaces

```rust
use std::cmp::min;
let least = min(7, 1); //this is 1
```

within "use" directives, curly brackets are "globs" (wtf)

```rust
use std::cmp::min;
use std::cmp::max;
//is the same as 
use std::cmp::{min, max};
//is the same as 
use std::{cmp::min, cmp::max};
```

use a wildcard to import every symbol from a namespace

```rust
use std::cmp::*;
```

types are also namespaces 

```rust
let x = "booyah".len(); //this is 6
let x = str::len("booyah"); //this is also 6
```

many types are in scope by default because rust inserts this at the beginning of every module

```rust
use std::prelude::v1::*;
```
which is why

```rust
let v = Vec::new();
//is the same as getting the full path
let v = std::vec::Vec::new();
```

Structs ? what are structs? 

```rust
struct Vec2 {
    x: f64, //64-bit float 
    y: f64,
}
```

structs are initialized by struct literals

```rust
let v1 = Vec2 { x: 1.0, y: 3.0 };
let v2 = Vec2 { y: 2.0, x: 4.0 };
```

shortcut for initializing fields from another struct
can only happen in the last position
cannot be followed by a comma 

```rust
let v3 = Vec2 { 
    x: 14.0, 
    ..v2
};
```

destructuring structs 

```rust
let v = Vec2 { x: 3.0, y: 6.0 };
let Vec2 { a, b } = v;
//a is 3.0, b is 6.0
```

throw away v.y:

```rust
let Vec2 { x, .. } = v;
```

### Patterns and Destructuring

