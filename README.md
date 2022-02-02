# learning-rust
Some simples programs to self-teach me the Rust Programming Language.
https://doc.rust-lang.org/book/ch01-01-installation.html


# Notes:

## rustup, rustc and cargo
* update rust `$ rustup update`
* check the version `$ rustc --version`
* check the documentation `$ rustup doc`

## writing and running an Hello World program
We must always have a `main` function, like C, and this is the first piece of code that is executed. 
```rust
// main.rs
fn main() {
    println!("Hello World!");
}
```
Compile and run the program: 
```bash
$ rustc main.rs
$ ./main
Hello World!
```
It worked! :)

It is important to note that `println!` doesn't call a function. Instead it calls a macro since we are using the `!` notation. To call the function one would write `println`. However, in this case, there is no function called `println`.

## Cargo
Acts like a makefile. It is usefull to build large projects with many crates (that is what header files are called in rust). Going to skip for now! For simple programs, `rustc` is easier.

## Guess the number game
The code can be found in the `guessing_game.rs` file.

Let's go through the program line by line:
1. `use std::io;` - includes the input/output library in the program. This comes with the standard library. By default rust includes automatically some files (see more [here](https://doc.rust-lang.org/std/prelude/index.html))
2. Next we need to store the guess from the user, so we will create a *variable* with the code `let mut guess = String::new();`. To create a new variable, we have to use the keyword `let`, eg. `let a = 5;`. In rust, by default, the variables are immutable (or `const` type in C++). If we desire to modify the value of some variable after initialization, we must add the key word `mut`. Here we declare a new variable called `guess` and assign it a value `String::new()`. 







